# 🚀 Curso Cypress Alura

Este repositório representa meu primeiro contato com testes
automatizados utilizando o Cypress, desenvolvido durante o curso da
Alura:

📚 [Cypress: Automatizando Testes E2E](https://cursos.alura.com.br/course/cypress-automatizando-testes-e2e)


O objetivo deste projeto é aplicar na prática os conceitos de testes
End-to-End (E2E), explorando execução via interface gráfica e modo
headless, além da geração de evidências e relatórios.

------------------------------------------------------------------------

## ⚙️ Instalação do Cypress

Antes de tudo, é necessário ter o npm inicializado no projeto:
```bash
npm init
```

Instale a versão específica do Cypress:
```bash
npm install cypress@13.6.4 --save-dev
```
------------------------------------------------------------------------

## ▶️ Executando o Cypress

Abrir interface gráfica:
```bash
npx cypress open
```
Executar em modo headless (via terminal):

Executar todos os testes:
```bash
npx cypress run
```
Executar um teste específico:
```bash
npx cypress run --spec .\cypress\e2e\login-correto.cy.js
```
------------------------------------------------------------------------

## 🛠 Possível erro

Caso ocorra o erro:

    Command timed out after 30000 milliseconds

Tente aumentar o tempo de verificação no arquivo:

    node_modules\cypress\lib\tasks\verify.js

Alterando a constante:

    VERIFY_TEST_RUNNER_TIMEOUT_MS

------------------------------------------------------------------------

## 🎥 Gerando Evidências (Vídeos)

No arquivo cypress.config.js, adicione dentro de e2e:
```bash
video: true,
```
Depois execute:
```bash
npx cypress run
```
------------------------------------------------------------------------

## 📊 Relatórios com Mochawesome

Instale o reporter:
```bash
npm install --save-dev mochawesome
```
Adicione no cypress.config.js após video: true:
```bash
    reporter: 'mochawesome',
    reporterOptions: {
      reportDir: 'cypress/results',
      overwrite: false,
      html: true,
      json: true,
      timestamp: "mmddyyyy_HHMMss",
      reportTitle: "Relatórios testes automatizados",
    }
```
Execute:
```bash
npx cypress run --reporter mochawesome
```
Será criada a pasta cypress/results com os relatórios em HTML e JSON.

Para unificar relatórios JSON:
```bash
npm install --save-dev mochawesome-merge
```
------------------------------------------------------------------------

## 🧠 Sobre o modo Headless

Executar testes em modo headless significa rodar sem interface gráfica.

✔️ Execução mais rápida
✔️ Ideal para pipelines de CI/CD
✔️ Pode rodar em containers Docker
✔️ Feedback automático a cada alteração no código

------------------------------------------------------------------------

## 🔄 Integração CI/CD

O Cypress pode ser integrado a pipelines como:

-   GitHub Actions
-   Jenkins

Também é possível utilizar o Cypress Cloud para monitoramento e análise
das execuções.

------------------------------------------------------------------------

✨ **Projeto com foco em aprendizado e evolução em testes automatizados
E2E.**
