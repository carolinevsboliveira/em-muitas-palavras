# Em muitas palavras

Um blog estático de resenhas de livros construído com Hugo e Hextra, com deploy automático via GitHub Pages.

> *"Um leitor vive mil vidas antes de morrer. Aquele que nunca lê vive apenas uma."* — George R.R. Martin

## ✨ Funcionalidades

- 📚 **Resenhas comentadas** — análises não profissionais de livros lidos
- 📊 **Estatísticas dinâmicas** — cards com livros lidos, resenhas em progresso e leituras atuais
- 🔖 **Badges de resenha** — indicadores visuais de status e sentimento das leituras
- 🌙 **Dark mode** — tema escuro integrado
- 🔍 **Busca integrada** — busca por títulos, autores e conteúdo
- ⚡ **Zero servidor** — conteúdo como código, versionado no Git
- 🚀 **Deploy automático** — atualiza com cada push via GitHub Actions

## Começar a usar

### Adicionar um novo card de leitura em progresso

Para adicionar um livro que está sendo lido atualmente, edite `content/_index.md` e atualize o shortcode `stats`:

```markdown
{{< stats read="6" reviews="2" reading="Título do Livro" author="Nome do Autor" >}}
```

- `read`: número de livros lidos em 2026
- `reviews`: número de resenhas em progresso
- `reading`: título do livro em leitura
- `author`: nome do autor

### Estrutura de resenhas

As resenhas ficam em `content/resenhas/` e são organizadas por livro:

```
content/resenhas/
├── livro1/
│   ├── _index.md (informações do livro)
│   └── resenha.md (conteúdo da resenha)
└── livro2/
    └── _index.md
```

## Quick Start

Use this template to create your own repository:

<img src="https://docs.github.com/assets/cb-77734/mw-1440/images/help/repository/use-this-template-button.webp" width=400 />

You can also quickly start developing using the following online development environment:

- [GitHub Codespaces](https://github.com/codespaces)

    [![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/imfing/hextra-starter-template)

    Create a new codespace and follow the [Local Development](#local-development) to launch the preview


## Deployment

### GitHub Pages

A GitHub Actions workflow is provided in [`.github/workflows/pages.yaml`](./.github/workflows/pages.yaml) to [publish to GitHub Pages](https://github.blog/changelog/2022-07-27-github-pages-custom-github-actions-workflows-beta/) for free. 

For details, see [Publishing with a custom GitHub Actions workflow](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-with-a-custom-github-actions-workflow).

Note: in the settings, make sure to set the Pages deployment source to **GitHub Actions**:

<img src="https://github.com/imfing/hextra-starter-template/assets/5097752/99676430-884e-42ab-b901-f6534a0d6eee" width=600 />

[Run the workflow manually](https://docs.github.com/en/actions/using-workflows/manually-running-a-workflow) if it's not triggered automatically.

### Netlify

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/imfing/hextra-starter-template)

### Vercel

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fimfing%2Fhextra-starter-template&env=HUGO_VERSION)

Override the configuration:

<img src="https://github.com/imfing/hextra-starter-template/assets/5097752/e2e3cecd-c884-47ec-b064-14f896fee08d" width=600 />

## Local Development

Pre-requisites: [Hugo](https://gohugo.io/getting-started/installing/), [Go](https://golang.org/doc/install) and [Git](https://git-scm.com)

```shell
# Clone the repo
git clone https://github.com/imfing/hextra-starter-template.git

# Change directory
cd hextra-starter-template

# Start the server
hugo mod tidy
hugo server --logLevel debug --disableFastRender -p 1313
```

### Update theme

```shell
hugo mod get -u
hugo mod tidy
```

See [Update modules](https://gohugo.io/hugo-modules/use-modules/#update-modules) for more details.

