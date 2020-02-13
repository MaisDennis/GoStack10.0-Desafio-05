<h1>Conceitos abordados:</h1>

1. Iniciar um projeto react-app.
2. Incluir ESLint, Prettier & EditorConfig.
3. Criar routes, pages (index e styles).
4. Utilizar Styled components para a estilização.
5. Criação de componentes.
   1. **state = {}, e render() {};**
   2. funções **handleInputChange, handleSubmit**
6. Utilizar a biblioteca axios para fazer requisições API e criar a baseURL.
7. Utilizar localStorage do browser.
   1. **componentDidMount e componentDidUpdate** (Carregar e Salvar no LocalStorage, respectivamente).
8. Utilizar o { Link } from 'react-router-dom'.

Novos:

1. check repositorio não encontrado e duplicado.
2. Filtro de estado de repositorio: Todos / Abertos / Encerrados.
3. PAginação da lista de issues.

<h1>Descrição do projeto:</h1>

<p>

Projeto base para o desafio:
https://github.com/MaisDennis/GoStack10.0-Modulo-05

Um site para buscar repositórios no Github, retornando o nome, a descrição e issues atuais presentes no repositório. A pagina principal cria uma lista de repositórios procurados, e em cada item, traz um link.

![Main](https://github.com/MaisDennis/GoStack10.0-Modulo-05/blob/master/src/assets/Main.png)

Novos Features:

<p>

<h1>Criando o projeto:</h1>

1. (1. e 2.) Criando a borda vermelha para repositorios não-encontrados e duplicados na pesquisa.
   1. Main/index.js:
      1. Incluir no state:
      ```Javascript
      border: false,
      ```
      2. Adicione try/catch na função handleSubmit com o checkRepoExists
      3. Form recebe a propriedade "border={border}". Estilizar props.border com a condicional border: red;

3. Filtro de estado:
   1. Repository/index.js
      1. Incluir no state:
          ```Javascript
          filter: {},
          ```
      2. Incluir o componente IssueFilter com select / option (all / open / closed) dentro.
      3. Estilizar Issue Filter, select.
      4. Criar as funções handleFilter e loadIssues. loadIssues: recarregar a lista, conforme componentDidMount.
         1. loadIssues params:
         ```Javascript
         params: {
          state: this.state.filter,
          page: this.state.page,
          per_page: 5,
         },
         ```

4. Paginação:
   1. Repository/index.js
      1. Incluir no state:
          ```Javascript
          page: 1,
          ```
      2. Incluir o componente PageActions com 2 buttons dentro: 'Anterior' e 'Próximo'.
      3. Estilizar.
      4. Criar a função handlePage.
         1. Vide IF para impedir a página "0".

