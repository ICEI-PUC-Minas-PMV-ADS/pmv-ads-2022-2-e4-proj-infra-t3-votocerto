
# Plano de Testes de Software


## Ferramentas de Testes (Opcional)

<span style="color:red">Pré-requisitos: <a href="2-Especificação do Projeto.md"> Especificação do Projeto</a></span>, <a href="3-Projeto de Interface.md"> Projeto de Interface</a>

Apresente os cenários de testes utilizados na realização dos testes da sua aplicação. Escolha cenários de testes que demonstrem os requisitos sendo satisfeitos.

Enumere quais cenários de testes foram selecionados para teste. Neste tópico o grupo deve detalhar quais funcionalidades avaliadas, o grupo de usuários que foi escolhido para participar do teste e as ferramentas utilizadas.
 
# Teste E2E

**Fullstack E2E -  Teste com Cypress + Cucumber**
Antes de começar:
Cypress é um framework utilizado para automação de testes end to end. Atualmente, utiliza JavaScript como linguagem de programação e executa os testes multiplataforma
Cucumber é uma ferramenta que pode ser utilizada em conjunto com o Cypress e permite a escrita de testes automatizados no formato Gherkin.

Exemplo:
@tag
Feature: Encontrar governador eleito para um determinado endereço

Scenario: Econtrar governador eleito de Minas Gerais
          Given Janaina mora em Belo Horizonte
          E     está quer saber quem é o governador de acordo com o seu endereço
          When  preenche o formulário com seus dados
          E     Seleciona apenas executivo estadual
          E     clica em "Encontrar eleitos"
          Then  O Governador Eleito "Romeo Zema" deve aparecer na tela
          
          
 
**Configurando Ambiente **
1 - Instalar o Node ( caso ainda já não esteja intalado)  
2 - Instalar Cypress Versão 8 ( Se intalar o 10, temos que rever como configirar o cucumber sem a pasta plugins.js)
2.1 - Crie uma pasta onde ficarão os arquivos do seu projeto. Abra o terminal do windows e acesse essa mesma pasta com o seguinte comando:
2.2 - Dentro da pasta do projeto, execute: npm install --save-dev cypress@8.0.0 cypress-cucumber-preprocessor
2.3 - Ainda dentro da pasta do projeto, execute: npx cypress open
3 - Configurar o Cucumber: 
3.1 - Adicione ao arquivo cypress/plugins/index.js o seguinte script:

const cucumber = require('cypress-cucumber-preprocessor').default
module.exports = (on, config) => {
  on('file:preprocessor', cucumber())
}

**Estruturando o projeto **
Optamos aqui por usar uma qrquitetura pageobjects

1 - integration: nesta pasta colocamos os nossos arquivos com os cenários de teste escritos no formato Gherkin.
2 - plugin/index.js: este arquivo é destinado para configuração de plugins. Utilizamos ele ao configurar o Cucumber
3 - support: dentro desta pasta colocamos os steps, os scripts e o mapeamento de elementos de nossos testes.
4 - node_modules: aqui ficam os arquivos de funcionamento do Cypress e do Cucumber. Normalmente não precisamos mexer nesta pasta.
5 - cypress.json: neste arquivo podemos realizar configurações globais do nosso projeto. Ex.: criar variáveis globais, definir resolução do navegador, setar uma URL padrão, entre outros. 

**Pastas Adcionais**
Precisamos criar três pastas em cypress/support, pois iremos utilizar o conceito de page object. São elas: elements, pageobjects e steps.

1 - Steps: nesta pasta colocamos os passos que farão a conexão entre o que escrevemos em Gherkin e os scripts que fazemos em Cypress.
2 - pageobjects: aqui deixamos os scripts feitos em Cypress.
A ideia do page objects é a de criarmos um arquivo.js para cada página ou fluxo do site. Dessa forma, mantemos a organização e facilitamos a manutenção do código, pois colocamos no arquivo os comandos que são executados na página/fluxo correspondentes ao nome do arquivo.
Ex.: HomePage.js, PdpPage.js, Checkout.js.
3  elements: possui o mesmo conceito do page objects, mas aqui colocamos os elementos da página. Tal organização permite que elementos sejam reutilizados e tenham fácil manutenção.
Ex.: HomeElements.js, PdpElements.js, CheckoutElements.js.

Além disso, pelo próprio VS Code, precisamos criar um arquivo na pasta raíz do projeto com o nome e formato package.json. Adicione a ele o seguinte script:
{
    "scripts": {
        "test:chrome": "cypress run --browser chrome --no-exit"
    },
    "cypress-cucumber-preprocessor": {
        "step_definitions": "cypress/support/steps"
    }
}


Configurar o arquivo cypress.json. Abaixo configuramos para nosso teste de exemplo.

{
    "viewportWidth": 1366,
    "viewportHeight": 768,
    "defaultCommandTimeout": 10000,
    "baseUrl": "https://votocerto.com.br/"
}

Criar um arquivo com o cenário de teste escrito em Gherkin. Ele deve ficar dentro de cypress/integration e ter a extensão .feature.

Feature: Login Voto Certo

    Scenario: Visualizar opção de recuperar senha esquecida
        Given acesso o site VotoCerto
        When acesso a pagina de login
        Then devo visualizar botao de recuperar senha esquecida
        
Criar um arquivo com os passos do teste. Ele deve ter formato .js e ficar dentro de cypress/support/steps. Criamos um arquivo de steps para cada arquivo de feature que temos e utilizamos o mesmo nome nos dois, apenas acrescentando “Steps”.

/* global Given, Then, When */

import LoginPage from '../pageobjects/LoginPage'
const loginPage = new LoginPage

Given("acesso o site CWI", () => {
    loginPage.acessarSite();
})

When("acesso a pagina de login", () => {
    loginPage.clicarBotaoPaginaLogin();
})

Then("devo visualizar botao de recuperar senha esquecida", () => {
    loginPage.visualizarBotaoRecuperarSenha();
})

Criar um arquivo com as funções e comandos que executaremos. Deve ter formato .js e ficar dentro de cypress/support/pageobjects.

/// <reference types="Cypress" />

import LoginElements from '../elements/LoginElements'
const loginElements = new LoginElements
const url = Cypress.config("baseUrl")

class LoginPage {
    // Acessa o site que será testado
    acessarSite() {
        cy.visit(url)
    }

    // Clica no botão que acessa a página de login do site
    clicarBotaoPaginaLogin() {
        cy.get(loginElements.botaoLogin()).click()
    }
  
    // Verifica se o botão tem o texto "Esqueceu sua senha?"
    visualizarBotaoRecuperarSenha() {
        cy.get(loginElements.botaoRecuperarSenha()).should('contain', 'Esqueceu sua senha?')
    }
}

export default LoginPage;



Criar o arquivo no qual faremos a listagem dos elementos da página. Deve ter formato .js e ficar dentro de cypress/support/elements.
class LoginElements {
  botaoLogin = () => { return '.header__profile-wrapper > :nth-child(2)' }

  botaoRecuperarSenha = () => { return '.login__form__forgot-password' }
}

export default LoginElements;


Eexecutar o teste. Após ter salvo todos os arquivos, execute pelo terminal do próprio VS Code o comando abaixo que configuramos no arquivo package.json:
npm run test:chrome  ou npx cypress run --browser chrome --no-exit

Comente sobre as ferramentas de testes utilizadas.
 
> **Links Úteis**:
> - [IBM - Criação e Geração de Planos de Teste](https://www.ibm.com/developerworks/br/local/rational/criacao_geracao_planos_testes_software/index.html)
> - [Práticas e Técnicas de Testes Ágeis](http://assiste.serpro.gov.br/serproagil/Apresenta/slides.pdf)
> -  [Teste de Software: Conceitos e tipos de testes](https://blog.onedaytesting.com.br/teste-de-software/)
> - [Criação e Geração de Planos de Teste de Software](https://www.ibm.com/developerworks/br/local/rational/criacao_geracao_planos_testes_software/index.html)
> - [Ferramentas de Test para Java Script](https://geekflare.com/javascript-unit-testing/)
> - [UX Tools](https://uxdesign.cc/ux-user-research-and-user-testing-tools-2d339d379dc7)
