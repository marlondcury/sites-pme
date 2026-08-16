# Landing Page — Marlon Domingos (Criação de Sites)

Site institucional/landing page para divulgação do serviço de criação de sites para pequenas e médias empresas.

## Estrutura

```
site-marlon-domingos/
├── index.html      # página única (HTML + CSS inline)
├── favicon.svg      # ícone do site
├── robots.txt        # instruções para buscadores
├── sitemap.xml       # mapa do site para SEO
└── README.md
```

## Como publicar (GitHub Pages — igual aos outros projetos)

1. Crie um repositório novo no GitHub (ex: `landing-marlondomingos`).
2. Suba todos os arquivos desta pasta para a raiz do repositório.
3. Vá em **Settings → Pages**, selecione a branch `main` e a pasta `/root`.
4. Aguarde alguns minutos — o site fica disponível em `https://seuusuario.github.io/nome-do-repo/`.

## Antes de publicar, ajuste:

- **WhatsApp**: número já configurado como `5533999744787` (troque em todos os links `wa.me` do `index.html` se mudar).
- **Domínio/canonical**: atualize a tag `<link rel="canonical">` e o `sitemap.xml` com a URL final.
- **Portfólio**: os cards de portfólio usam mockups em CSS — se quiser, troque por prints reais dos sites (Godinho, Taste Gastronomia, CA-SI UFES).
- **Imagem de compartilhamento (og:image)**: ainda não configurada — vale gerar uma imagem 1200x630 e adicionar a tag `og:image` no `<head>`.
# landing-sites
