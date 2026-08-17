# sites-pme — Landing Page (CriaSite)

Site institucional/landing page da marca **CriaSite**, de Marlon Domingos, para divulgação do serviço de criação de sites para pequenas e médias empresas.

## Sobre o domínio

O nome de marca escolhido foi **CriaSite**. Quando comprar o domínio (ex: `criasite.com.br` no [registro.br](https://registro.br/busca-dominio)), me avise para eu atualizar o `canonical`, `sitemap.xml`, `robots.txt` e o schema.org do `index.html`, além de configurar o domínio próprio no GitHub Pages (arquivo `CNAME`).

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
4. Aguarde 1–2 minutos. O site fica em `https://marlondcury.github.io/sites-pme/`.

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
- **Domínio/canonical**: já apontando para `https://marlondcury.github.io/sites-pme/` — atualize a tag `<link rel="canonical">`, o `sitemap.xml` e o `robots.txt` se usar um domínio próprio.
- **Portfólio**: os cards de portfólio usam mockups em CSS — se quiser, troque por prints reais dos sites (Godinho, Taste Gastronomia, CA-SI UFES) em `assets/images/`.
- **Imagem de compartilhamento (og:image)**: ainda não configurada — vale gerar uma imagem 1200x630, salvar em `assets/images/` e adicionar a tag `og:image` no `<head>` do `index.html`.

## Desenvolvimento local

Não há build nem dependências (sem `package.json`, sem `npm install`). Basta abrir o `index.html` direto no navegador, ou rodar um servidor local simples:

```
python3 -m http.server 8000
```

e acessar `http://localhost:8000`.
