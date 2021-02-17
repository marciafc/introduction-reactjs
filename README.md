# Introdução ao ReactJS

- lesson-01

  - Renderização (pasta renderization)

  - Componentes (pasta components)

  - Ciclo de Vida (pasta lifecycle)

  - Configurar um projeto do zero

    - [Passos descritos abaixo em "Criar projeto do zero"](#Criar-projeto-do-zero)

      - exemplo (by me) pasta 'my-first-project'

      - outro exemplo projeto inicial na pasta 'configuration'. Rodar direto os comandos:
        ```shell
          npm install
          npm start
        ```

  - Exemplo JSX (pasta jsx)

## Executar exemplos

1. Acessar a pasta com o assunto a visualizar

```shell
   $ cd lesson-01/renderization/
```

2. Executar os comandos

```shell
  $  npm install

  $  npm start
  OU
  $  npm run start
```

## React Developer Tools

"**_The Components tab shows you the root React components that were rendered on the page, as well as the subcomponents that they ended up rendering_**.

**_By selecting one of the components in the tree, you can inspect and edit its current props and state in the panel on the right. In the breadcrumbs you can inspect the selected component, the component that created it, the component that created that one, and so on._**"

- [Extensão do Chrome](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi)
  - Exibe atualização na tela (tela "pisca" quando ocorre atualização)
    - Highlight updates when components render
  - Exibe hierarquia, props, children
  - Exibe o state

<img src="img/react_dev-tools_config1.png">

<img src="img/react_dev-tools_config2.png">

<img src="img/react_dev-tools.png">

<img src="img/react_dev-tools2.png">

<img src="img/react_dev-tools3.png">

### Estado e ciclo de vida do ReactJS

Artigo sobre [Métodos do ciclo de vida de componentes ReactJS — Um mergulho profundo!](https://medium.com/creditas-tech/m%C3%A9todos-do-ciclo-de-vida-de-componentes-reactjs-um-mergulho-profundo-332ed7b3b782)

- Inicialização
  - props e state
- Montagem
  - componentWillMount (versão 17 removido)
  - render
  - componentDidMount
- Atualização
  - props
    - componetWillReceiveProps
    - shouldComponentUpdate
    - componentWillUpdate
    - render
    - componentDidUpdate
  - state
    - shouldComponentUpdate
    - componentWillUpdate
    - render
    - componentDidUpdate
- Desmontagem
  - componentWillUnmount

-> Cuidar com **gargalo de performance**: atualização de cada "pedaço", renderização demasiada (muito "re-render"), por não saber usar corretamente **shouldComponentUpdate**, **componentWillUpdate** e **componentDidUpdate**.

## Configuração

- React Create App

- React Scripts

- Task Runners e Bundler Sizers

## Criar projeto do zero

```shell

  $ mkdir my-first-project

  $ cd my-first-project

  $ npm init

  vários enters...

  $ yes

  $ npm install --save react@16.8.6 react-dom@16.8.6 react-scripts@3.0.1

      -> react-scripts : monta um servidor, não precisa configurar

  Alterar no arquivo "package.json":
    - incluir respectivos scripts em "scripts"
    - "main": "src/index.js"
    - inclur "devDependencies" com "typescript"

  Na raiz, criar pasta "public"

  Dentro da pasta "public", criar um arquivo "index.html" "basicão"
    - Dentro do "body" deve conter "div" com id="root"

    <!DOCTYPE html>
    <html lang="en">

    <head>
      <title>React App</title>
    </head>

    <body>
      <div id="root"></div>
    </body>

    </html>

Na raiz, criar pasta "src"

Dentro da pasta "src", criar dois arquivos: "index.js" e "styles.css"

  // **** index.js ****
  import React from "react";
  import ReactDOM from "react-dom";
  import "./styles.css";

  const App = () => {
    return <div className="App">Hello World</div>;
  };

  const rootElement = document.getElementById("root");
  ReactDOM.render(<App />, rootElement);

  // **** styles.css ****
  * {
    margin: 0;
    padding: 0;
  }

  body {
    font-size: 22px;
  }

  $ npm start


```

## JSX

- Não é obrigatório utilizar JSX
- Sintax Suggar para React.createElement
- Browser nao interpreta JSX... necessário transpilador (exemplo, o Babel)
