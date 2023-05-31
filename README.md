# Projeto Vite Vue3 TypeScript

Este projeto é uma aplicação web desenvolvida utilizando as seguintes tecnologias:

- [Vite](https://vitejs.dev/): Um build tool e bundler extremamente rápido para projetos web.
- [Vue 3](https://v3.vuejs.org/): Um framework JavaScript progressivo para construir interfaces de usuário.
- [TypeScript](https://www.typescriptlang.org/): Uma linguagem de programação que adiciona tipagem estática ao JavaScript.

## Arquitetura do Projeto

A estrutura do projeto é organizada da seguinte forma:

```
src
├── views
│   ├── MainPage.vue
│   └── ...
├── components
│   ├── SearchBar.vue
│   ├── ListNews.vue
│   ├── NewCard.vue
│   └── ...
└── assets
    ├── styles
    │   └── main.scss
    └── ...
```

- **views**: Esta pasta contém as visualizações (ou páginas) principais da aplicação. Por exemplo, o arquivo `MainPage.vue` representa a página principal do projeto.
- **components**: Nesta pasta estão os componentes reutilizáveis da aplicação. Cada componente é armazenado em seu próprio arquivo Vue. Alguns exemplos de componentes incluem `SearchBar.vue`, `ListNews.vue` e `NewCard.vue`.
- **assets**: Aqui são armazenados os ativos estáticos da aplicação, como imagens, fontes e arquivos de estilo. A pasta `styles` contém o arquivo `main.scss`, que é responsável por fornecer estilos globais para a aplicação.

## Funcionalidades

Este projeto também faz chamadas para a API de notícias [NewsAPI](https://newsapi.org/). A API é utilizada para recuperar as notícias mais recentes com base em palavras-chave e categorias selecionadas.

As chamadas para a API são feitas no componente `MainPage.vue`, utilizando o método `fetchNews`. O endpoint utilizado é `https://newsapi.org/v2/top-headlines`, onde são passados parâmetros como país, palavra-chave e categoria para obter as notícias desejadas.

## Executando o Projeto Localmente

Para executar o projeto localmente, siga estas etapas:

1. Certifique-se de ter o Node.js instalado em sua máquina.
2. Clone o repositório do projeto.
3. Abra o terminal na raiz do projeto.
4. Execute o comando `npm install` para instalar as dependências.
5. Abra o arquivo `MainPage.vue` e substitua a variável `apiKey` pelo seu próprio valor da chave de API da NewsAPI.
6. Execute o comando `npm run dev` para iniciar o servidor de desenvolvimento.
7. Acesse `http://localhost:5173` em seu navegador para visualizar a aplicação em execução.

Agora você pode explorar o projeto, fazer pesquisas de notícias e visualizar os resultados obtidos da API da NewsAPI.

Divirta-se explorando o projeto Vite Vue3 TypeScript e as notícias fornecidas pela API!
