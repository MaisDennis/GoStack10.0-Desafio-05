# GoStack 10.0 || Desafio 05

* [1. Conceitos abordados](#1-conceitos-abordados)
* [2. Descrição do projeto](#2-descrição-do-projeto)
* [3. Enunciado do Projeto](#3-enunciado-do-projeto)
* [4. Criando o projeto](#4-criando-o-projeto)

##  1. Conceitos abordados

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

##  2. Descrição do projeto

<p>

Projeto base para o desafio:
https://github.com/MaisDennis/GoStack10.0-Modulo-05

Um site para buscar repositórios no Github, retornando o nome, a descrição e issues atuais presentes no repositório. A pagina principal cria uma lista de repositórios procurados, e em cada item, traz um link.

### Main
<img src="https://github.com/MaisDennis/GoStack10.0-Modulo-05/blob/master/src/assets/Main.png" alt="Main" width="100%" height="auto">

### Repo
<img src="https://github.com/MaisDennis/GoStack10.0-Modulo-05/blob/master/src/assets/Repo.png" alt="Main" width="100%" height="auto">

### Issue
<img src="https://github.com/MaisDennis/GoStack10.0-Modulo-05/blob/master/src/assets/Issue.png" alt="Main" width="100%" height="auto">

Novos Features:

<p>

##  3. Enunciado do Projeto

<h1 align="center">
    <img alt="GoStack" src="https://rocketseat-cdn.s3-sa-east-1.amazonaws.com/bootcamp-header.png" width="200px" />
</h1>

<h3 align="center">
  Desafio 5: Primeiro projeto com ReactJS
</h3>

<p align="center">“Para quem fica melhor a cada dia, ficar pronto é utopia”!</blockquote>

<p align="center">
  <img alt="GitHub language count" src="https://img.shields.io/github/languages/count/rocketseat/bootcamp-gostack-desafio-05?color=%2304D361">

  <a href="https://rocketseat.com.br">
    <img alt="Made by Rocketseat" src="https://img.shields.io/badge/made%20by-Rocketseat-%2304D361">
  </a>

  <img alt="License" src="https://img.shields.io/badge/license-MIT-%2304D361">

  <a href="https://github.com/Rocketseat/bootcamp-gostack-desafio-05/stargazers">
    <img alt="Stargazers" src="https://img.shields.io/github/stars/rocketseat/bootcamp-gostack-desafio-05?style=social">
  </a>
</p>

<p align="center">
  <a href="#rocket-sobre-o-desafio">Sobre o desafio</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#-entrega">Entrega</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#memo-licença">Licença</a>
</p>

## :rocket: Sobre o desafio

Nesse desafio você adicionará novas funcionalidades na aplicação que desenvolvemos ao longo desse módulo.

### Funcionalidades

#### 1. Captando erros

Adicione um `try/catch` por volta do código presente na função `handleSubmit` presente no componente `Main` e caso um repositório não seja encontrado na API do Github adicione uma borda vermelha por volta do input em que o usuário digitou o nome do repositório.

#### 2. Repositório duplicado

Antes de fazer a chamada à API na função `handleSubmit` faça uma verificação para ver se o repositório não está duplicado, ou seja, se ele ainda não existe no estado de `repositories`.

Caso exista, dispare um erro, e com isso o código cairá no `catch` do `try/catch` criado na funcionalidade anterior.

```js
throw new Error('Repositório duplicado');
```

#### 3. Filtro de estado

Adicione um filtro de estado na listagem de Issues que criamos no detalhe do repositório. O estado representa se a issue está em aberto, fechada ou uma opção para exibir todas.

Exemplos de requisição:

```
https://api.github.com/repos/rocketseat/unform/issues?state=all
https://api.github.com/repos/rocketseat/unform/issues?state=open
https://api.github.com/repos/rocketseat/unform/issues?state=closed
```

Você pode encontrar a documentação [nesse link](https://developer.github.com/v3/issues/#parameters-1);

#### 4. Paginação

Adicione paginação nas issues listadas no detalhe do repositório. A API do Github lista no máximo 30 issues por página e você pode controlar o número da página atual por um parâmetro no endereço da requisição:

```
https://api.github.com/repos/rocketseat/unform/issues?page=2
```

Adicione apenas um botão de próxima página e página anterior. O botão de página anterior deve ficar desativado na primeira página.

## 📅 Entrega

Esse desafio **não precisa ser entregue** e não receberá correção, mas você pode ver o resultado do [código do desafio aqui](https://github.com/Rocketseat/bootcamp-gostack-desafio-05). Após concluir o desafio, adicionar esse código ao seu Github é uma boa forma de demonstrar seus conhecimentos para oportunidades futuras.

## :memo: Licença

Esse projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE.md) para mais detalhes.

---

Feito com ♥ by Rocketseat :wave: [Entre na nossa comunidade!](https://discordapp.com/invite/gCRAFhc)

##  4. Criando o projeto

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

