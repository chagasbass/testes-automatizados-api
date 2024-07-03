## Fluxo de Teste Detalhado para Coleção Postman: Testes-Automatizados-API

## Introdução

Este documento detalha o fluxo de testes automatizados para a coleção Postman "Testes-Automatizados-API". O fluxo engloba diversos casos de teste relacionados ao gerenciamento de usuários e produtos em uma aplicação.

## Ordem de Execução:

* Erro ao cadastrar usuário
* Sucesso ao cadastrar usuário
* Sucesso ao listar usuários
* Sucesso ao listar usuário por email
* Erro ao listar usuário
* Sucesso ao efetuar o login
* Erro ao efetuar o login
* Erro de token ao cadastrar um produto
* Erro ao cadastrar um produto
* Sucesso ao cadastrar um produto
* Sucesso ao listar um produto
* Erro na exclusão de um usuário
* Sucesso na exclusão de um usuário

## Fluxo de Teste

### 1. Cadastro de Usuário

#### 1.1. Erro ao Cadastrar Usuário
    Deve retornar status code 400 quando senha não for informada. Efetuar o cadastro de um novo usuário e não passar o conteúdo do campo senha

#### 1.2. Sucesso ao Cadastrar Usuário
    * [Deve retornar status code 201 na tentativa de criação de um novo usuário]

### 2. Listagem de Usuários

#### 2.1. Sucesso ao Listar Usuários
    * [Deve retornar status code 200 quando a  listagem de usuários retornar resultados ]

#### 2.2. Sucesso ao Listar Usuário por Email
    * [Incluir o caso de teste detalhado para o sucesso na listagem de usuário por email]

#### 2.3. Erro ao Listar Usuário
    * [Incluir o caso de teste detalhado para o erro na listagem de usuário]

### 3. Autenticação

#### 3.1. Sucesso ao Efetuar o Login
    * [Incluir o caso de teste detalhado para o sucesso no login]

#### 3.2. Erro ao Efetuar o Login
    * [Incluir o caso de teste detalhado para o erro no login]

### 4. Gerenciamento de Produtos

#### 4.1. Erro de Token ao Cadastrar um Produto
    * [Incluir o caso de teste detalhado para o erro de token no cadastro de produto]

#### 4.2. Erro ao Cadastrar um Produto
    * [Incluir o caso de teste detalhado para o erro no cadastro de produto]

#### 4.3. Sucesso ao Cadastrar um Produto
    * [Incluir o caso de teste detalhado para o sucesso no cadastro de produto]

#### 4.4. Sucesso ao Listar um Produto
    * [Incluir o caso de teste detalhado para o sucesso na listagem de produto]

### 5. Exclusão de Usuário

#### 5.1. Erro na Exclusão de um Usuário
    * [Incluir o caso de teste detalhado para o erro na exclusão de usuário]

#### 5.2. Sucesso na Exclusão de um Usuário
    * [Incluir o caso de teste detalhado para o sucesso na exclusão de u