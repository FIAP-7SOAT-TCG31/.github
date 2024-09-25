# Tech Challenge FIAP Project - Fase 3

Este projeto foi desenvolvido durante a `Fase III`, do curso de `Arquitetura de Software` da FIAP, como requisito para avaliação.

## Integrantes do Grupo 7SOAT-31:

- Julio Augusto Silva (RM355432)
- Lucas Henrique de Oliveira Silva (RM354904)
- Getúlio Magela Silva (RM355427)
- Lucas Rego Lima (RM356101)
- Lilian Rosario de Jesus (RM355928)

## Demosntração em Vídeo

- [Assistir a Fase 1 no YouTube](https://www.youtube.com/watch?v=I0tNdblTFDc)
- [Assistir a Parte 1 da Fase 2 no YouTube](https://www.youtube.com/watch?v=r81e0Y-HJx4)
- [Assistir a Parte 2 da Fase 2 no YouTube](https://www.youtube.com/watch?v=cL7ryiqxlvk)
- [Assistir a Fase 3 no YouTube](TODO: Gravar o vídeo)

## Event Storming :[Ver no Miro 👁️](https://miro.com/app/board/uXjVKYNMy0E=/?moveToWidget=3458764595664040196&cot=10):

![Event Storming](../docs/resources/EventStormingEventFlow.png)

## Event Storming - Aggregates :[Ver no Miro 👁️](https://miro.com/app/board/uXjVKYNMy0E=/?moveToWidget=3458764589190621319&cot=14):

![Domain Aggregates](../docs/resources/EventStormingAggregates.png)

## Arquitetura Cloud (AWS) :[Ver no Miro 👁️](https://miro.com/app/board/uXjVKYNMy0E=/?moveToWidget=3458764601113929087&cot=10)

![Arquitetura Cloud (AWS)](../docs/resources/ArchitectureAwsCloud.png)

## Banco de Dados:

Foi escolhido o Postgres na AWS com RDS por ser um banco bastante flexível e com bom custo benefício. Além disso, o time também possui mais domínio com bancos relacionais, facilitando a modelagem e evolução das atividades. O postgres também é um banco leve para se rodar em ambiente local para desenvolvimento, melhorando a experiência de desenvolvimento.

## Modelagem da Base: [Ver no Miro 👁️](https://miro.com/app/board/uXjVKYNMy0E=/?moveToWidget=3458764600308284100&cot=14)

![Modelagem da Base](../docs/resources/DatabaseStructure.png)

## Repositórios

Foram criados 6 repositórios conforme as descrições abaixo:

- Repositório central para organizar a documentação da solução: [Ver Repositório](https://github.com/FIAP-7SOAT-TCG31/.github)

- Repositório central para provisionar e gerenciar o APIGateway que expõe tanto a Lambda de autenticação quanto o acesso à nossa aplicação no EKS com terraform: [Ver Repositório](https://github.com/FIAP-7SOAT-TCG31/fiap-7soat-tcg31-gateway)

- Repositório para provisionar a infraestrutura de banco de dados RDS com terraform: [Ver Repositório](https://github.com/FIAP-7SOAT-TCG31/fiap-7soat-tcg31-database)

- Repositório para provisionar a infraestrutura do EKS com terraform: [Ver Repositório](https://github.com/FIAP-7SOAT-TCG31/fiap-7soat-tcg31-kubernetes)

- Repositório para o serviço de autenticação serverless escrito com Typescript e implantado como um Lambda: [Ver Repositório](https://github.com/FIAP-7SOAT-TCG31/fiap-7soat-tcg31-lambda)

- Repositório para o serviço principal (fiap-burger) escrito com Java e Spring e implantado na infraestrutura do EKS: [Ver Repositório](https://github.com/FIAP-7SOAT-TCG31/fiap-7soat-tcg31-app)

## CICD

- Todos os repositórios estão com esteiras automatizadas para implantação.
- Todos os repositórios possuem proteções na branch principal (main), requisitando Pull Request com duas aprovações e que todos os checks de pipe tenham passado antes de realizar o merge.

## OpenAPI - Swagger

- O arquivo está disponibilizado em `../docs/swagger/openapi.yaml` e pode ser importado no [editor da OpenAPI](https://editor.swagger.io).

## Requisitos Funcionais:

- Cadastro de Clientes - Identity
- Cadastro de Itens - Somente ADMINs
- Gestão de Pedidos
  - Inclusão de Itens
  - Confirmação (Checkout)
  - Confirmação de Pagamento (Webhook)
  - Followup

## Requisitos Não Funcionais:

- Utilizar recurso serverless para identidade - Lambda
- Utilizar IDP para dados de identidade - Cognito
- Ambiente em núvem (Cloud AWS)
- Banco de dados em núvem (RDS - Postgres)
- App principal rodando em cluster Kubernetes em nuvem (EKS)
- Infraestrutura automatizada (terraform)
- Pipelines CICD automatizados (github actions)
- Branchs protegidas (PR, 2 approvals e actions passando)
