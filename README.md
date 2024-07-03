## TESTES AUTOMATIZADOS DE API COM POSTMAN E NEWMAN

**Introdução**

Este documento detalha o processo de criação de testes automatizados para uma API utilizando Postman e Newman, em formato Markdown. O objetivo é guiar o leitor na criação de um plano de testes, implementação dos testes no Postman, execução dos testes com Newman e geração de relatórios.

**Pré-requisitos**

* Ferramenta Postman instalada: [https://www.postman.com/downloads/](https://www.postman.com/downloads/)
* Node.js instalado: [https://nodejs.org/en/download/package-manager](https://nodejs.org/en/download/package-manager)
* Pacote newman-reporter-htmlextra instalado globalmente: `npm install -g newman-reporter-htmlextra`

**Etapas**

**1. Criação e Documentação do Plano de Teste**

* Definir a ordem de execução dos testes para os endpoints da API.
* Documentar os casos de teste de forma detalhada, incluindo:
    * Nome do caso de teste
    * Descrição
    * Pré-requisitos
    * Etapas do teste
    * Validações
    * Observações

**2. Configuração do Workspace e da Collection no Postman**

* Criar um Workspace no Postman.
* Importar a collection "Testes-Automatizados-API" para o Workspace.

**3. Criação de Variáveis de Ambiente**

* No Workspace, criar uma variável de ambiente nomeada `baseURL` e definir o valor como a URL base da API: `https://serverest.dev/`.

**4. Criação dos Testes**

**4.1. Snippet para Geração de Dados Fake**

* Incluir o seguinte snippet na aba "Pre-req" do teste:

```javascript
const email = `chagas.${new Date().getTime()}@gmail.com`;
const nomeUsuario = `Thiago ${new Date().getTime()}`;

pm.collectionVariables.set('emailUsuario', email);
pm.collectionVariables.set('nomeUsuario', nomeUsuario);
```

* Exemplo de teste criando no postman na aba "Post-res" 

```javascript
pm.test('Deve retornar status code 201 quando cadastro de usuário for efetuado com sucesso', () =>{
pm.response.to.have.status(201);
const retorno = pm.response.json();

pm.expect(retorno.message).to.not.null;
pm.expect(retorno._id).to.not.null;
pm.expect(retorno.message).to.equal("Cadastro realizado com sucesso");

pm.collectionVariables.set("idUsuario",retorno._id);

});
```


Após efetuar a criação dos testes de acordo com o plano de testes,
deve-se exportar a collection criada.

## INSTALAÇÃO NEWMAN

Fazer a instalação no newman 
~~~js
npm i -g newman
~~~
entrar no diretório da collection exportada e executar:

~~~js
newman run nome_arquivo
~~~

~~~js
newman run nome_arquivo

newman run Testes-Automatizados-API.postman_collection.json

~~~


### Executar com mais iterações

~~~js
newman run nome_arquivo --iteration-count QUANTIDADE

newman run Testes-Automatizados-API.postman_collection.json --iteration-count 10
~~~

## GERAÇÃO DE RELATÓRIOS COM NEWMAN

Para efetuar a geração dos relatórios dos testes instalar a lib newman-reporter-htmlextra

~~~js
npm install -g newman-reporter-htmlextra
~~~

### Comando para gerar o relatórios

~~~js
newman run nome_arquivo -r htmlextra

newman run Testes-Automatizados-API.postman_collection.json -r htmlextra
~~~

gerar o relatório passando um titulo, um título de janela de navegador e adicionando uma barra de progresso ao executar

~~~js
newman run Testes-Automatizados-API.postman_collection.json -r htmlextra
 --reporter-htmlextra-browserTitle "Relatório de Testes automatizados"
 --reporter-htmlextra-title "Api ServeRest"
 --reporter-htmlextra-displayProgressBar
 ~~~