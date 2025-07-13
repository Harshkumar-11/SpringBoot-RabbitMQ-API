# 🐇 Spring Boot RabbitMQ Producer-Consumer API

A simple Spring Boot application that demonstrates how to send and receive messages via **RabbitMQ** using REST endpoints. Ideal for microservices communication, task queues, and decoupled systems.

---

## 🚀 Features

- Send messages to a RabbitMQ queue using a `POST /produce` endpoint  
- Receive messages from the same queue using a `GET /consume` endpoint  
- Works without Postman — use `curl`, browser, or any REST client  
- Clean Java Spring Boot + RabbitMQ integration

---

## 🛠️ Setup Instructions

### 1️⃣ Create the Project

- Go to [https://start.spring.io](https://start.spring.io)
- Choose:
  - **Project:** Maven
  - **Language:** Java
  - **Dependencies:** Spring Web
- Click **Generate**, then unzip the file

### 2️⃣ Import into IntelliJ

- Open IntelliJ IDEA
- Click `File > Open` → Select the folder you just unzipped

### 3️⃣ Add RabbitMQ Dependency

In your `pom.xml`, add:

```xml
<dependency>
    <groupId>com.rabbitmq</groupId>
    <artifactId>amqp-client</artifactId>
    <version>5.25.0</version>
</dependency>

