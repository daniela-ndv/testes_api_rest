# Introdução a Testes de API Rest

Conceitos abordados no curso de **Testes de API Rest**, de [Julio de Lima no Youtube](https://www.youtube.com/watch?v=VqVQ7vHY32o&list=PLf8x7B3nFTl17WeEVj405tHlstiq1kNBX). 

### Tópicos explorados no curso: 
* Introdução a API Rest.
* Arquitetura: Service, Repository e Controller.
* Request e Response.
* Headers.
* Parâmetros.
* Autenticação e Autorização.
* Insomnia.
* Postman.
* RestAssured.
* Estratégia de Testes de API Rest.
* Cobertura de Testes.
* Testes funcionais.
* Testes de Performance.
* Teste de Compatibilidade.
* Mountebank.
* JSONSchema.
* Leitura de logs.

---

### Estrutura para rodar o projeto

Como base, é utilizada a API em Java de [AntonioMontanha/gerenciador-viagens](https://github.com/AntonioMontanha/gerenciador-viagens).  

Pré-requisitos (programas que devem estar instalados):
* JRE e JDR
* Intellij
* Maven (gestor de projetos)
* Git 

### Comando para rodar a API

Aapós configurar a API em seu ambiente, execute o comando abaixo:

      mvn spring-boot:run

A API será iniciada e estará disponível localmente na porta indicada no terminal de execução.

--- 

-> Outros detalhes sobre procedimentos técnicos se encontram na pasta `docs`.