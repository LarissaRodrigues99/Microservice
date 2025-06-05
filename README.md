# Microservice
Criando um microserviço usando fila de mensageria para enviar um email de boas vindas toda vez que um novo usuário se cadastrar.

# 📦 Sistema de Usuários e Envio de E-mails

Este projeto é composto por dois microsserviços desenvolvidos com **Java 21**, utilizando o ecossistema **Spring (Boot, JPA, Web, Mail, Validation)**, **PostgreSQL** como banco de dados, **RabbitMQ** como fila de mensagens, e **Maven** para gerenciamento de dependências.

## 🧱 Estrutura do Projeto

O sistema é dividido em dois repositórios/módulos principais:

- **Usuário Service**: Responsável pelo cadastro e gestão de usuários.
- **E-mail Service**: Responsável pelo envio de e-mails com base nas mensagens recebidas via RabbitMQ.

## 🔧 Tecnologias Utilizadas

- Java 21
- Spring Boot
  - Spring Web
  - Spring Data JPA
  - Spring Mail
  - Spring Validation
- PostgreSQL
- RabbitMQ
- Maven

## 🔗 Comunicação entre Serviços

A comunicação entre os serviços é feita de forma assíncrona através de **RabbitMQ**. Quando um novo usuário é criado, o serviço de Usuário envia uma mensagem para a fila, que é então consumida pelo serviço de E-mail para envio de uma notificação.

```
