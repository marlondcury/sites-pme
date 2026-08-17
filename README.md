# sites-pme — Landing Page (CriaSite)

Site institucional/landing page da marca **CriaSite**, de Marlon Domingos, para divulgação do serviço de criação de sites para pequenas e médias empresas.

## Domínio próprio: criesite.com (Hostinger + GitHub Pages)

O domínio `criesite.com` foi comprado na Hostinger. `canonical`, `sitemap.xml`, `robots.txt`, o schema.org e o arquivo `CNAME` já estão configurados para ele neste projeto. Faltam dois passos: apontar o DNS na Hostinger e ativar o domínio no GitHub Pages.

### 1. DNS na Hostinger

No painel da Hostinger → **Domínios** → `criesite.com` → **DNS / Nameservers** → **Gerenciar registros DNS**, adicione:

**Registros A** (apontam o domínio raiz `criesite.com` para o GitHub Pages) — adicione os 4:

| Tipo | Nome/Host | Aponta para       |
|------|-----------|--------------------|
| A    | @         | 185.199.108.153     |
| A    | @         | 185.199.109.153     |
| A    | @         | 185.199.110.153     |
| A    | @         | 185.199.111.153     |

**Registro CNAME** (para `www.criesite.com` também funcionar):

| Tipo  | Nome/Host | Aponta para              |
|-------|-----------|---------------------------|
| CNAME | www       | marlondcury.github.io     |

Remova/edite qualquer registro A ou CNAME antigo que a Hostinger tenha criado por padrão apontando pro "parking page" dela, senão eles conflitam.

### 2. GitHub Pages

1. No repositório `sites-pme` → **Settings → Pages**.
2. Em **Custom domain**, digite `criesite.com` → **Save**. Isso confirma o arquivo `CNAME` que já está na raiz deste projeto.
3. Aguarde a propagação do DNS (pode levar de alguns minutos até 24h). O GitHub mostra um aviso verde quando o DNS for verificado.
4. Depois que verificar, marque **Enforce HTTPS** (pode demorar um pouco pra ficar disponível — o certificado é gerado automaticamente).

Depois de propagado, o site fica em `https://criesite.com/` (e `https://www.criesite.com` redireciona pra lá também).

## Estrutura do projeto

```
sites-pme/
├── index.html            # marcação HTML (semântica, SEO, schema.org)
├── assets/
│   ├── css/
│   │   └── style.css     # todos os estilos
│   ├── js/
│   │   └── main.js       # menu mobile (abrir/fechar)
│   └── images/
│       └── favicon.svg   # ícone do site
├── robots.txt             # instruções para buscadores
├── sitemap.xml             # mapa do site para SEO
├── .nojekyll                # impede o GitHub Pages de processar via Jekyll
└── README.md
```

## Como publicar no GitHub Pages

1. Copie **todo o conteúdo desta pasta** (não a pasta em si) para a raiz do repositório `sites-pme`.
2. Confirme que `index.html` aparece na raiz do repositório no GitHub (aba **Code**), não dentro de uma subpasta.
3. No repositório, vá em **Settings → Pages** → em "Build and deployment", selecione **Deploy from a branch** → branch `main`, pasta `/ (root)` → **Save**.
4. Aguarde 1–2 minutos. O site fica em `https://marlondcury.github.io/sites-pme/` até o domínio próprio ser configurado (veja seção abaixo).

### Se o push der "repository not found"

Confirme que o remote local aponta pro nome certo do repositório:

```
git remote -v
git remote set-url origin https://github.com/marlondcury/sites-pme.git
```

### Se aparecer o README.md no lugar do site

Confirme que existe um `index.html` na raiz do repositório (não só o README) e que o arquivo `.nojekyll` foi commitado. Depois:

```
git add .
git commit -m "adicionar estrutura completa do site"
git push
```

## Antes de publicar, ajuste

- **WhatsApp**: número já configurado como `5533999744787` (troque em todos os links `wa.me` do `index.html` se mudar).
- **Domínio/canonical**: já apontando para `https://criesite.com/` (tag `<link rel="canonical">`, `sitemap.xml`, `robots.txt` e schema.org).
- **Portfólio**: os cards de portfólio usam mockups em CSS — se quiser, troque por prints reais dos sites (Godinho, Taste Gastronomia, CA-SI UFES) em `assets/images/`.
- **Imagem de compartilhamento (og:image)**: ainda não configurada — vale gerar uma imagem 1200x630, salvar em `assets/images/` e adicionar a tag `og:image` no `<head>` do `index.html`.

## Desenvolvimento local

Não há build nem dependências (sem `package.json`, sem `npm install`). Basta abrir o `index.html` direto no navegador, ou rodar um servidor local simples:

```
python3 -m http.server 8000
```

e acessar `http://localhost:8000`.
