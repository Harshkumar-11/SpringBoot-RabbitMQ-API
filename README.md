# 🐇 Spring Boot RabbitMQ Producer-Consumer API

A simple Spring Boot application that demonstrates how to send and receive messages using **RabbitMQ** via RESTful endpoints. This project is ideal for learning microservice communication, building task queues, or decoupling service logic.

---

## 🚀 Features

- 📤 Send messages to RabbitMQ using a `POST /produce` endpoint  
- 📥 Receive messages using a `GET /consume` endpoint  
- 💡 Works with curl, browser, or any REST client — no need for Postman  
- 🔧 Clean integration of Spring Boot and RabbitMQ

---

## 🛠️ Setup Instructions

### 1️⃣ Create the Project

- Go to [https://start.spring.io](https://start.spring.io)
- Choose:
  - **Project:** Maven
  - **Language:** Java
  - **Dependencies:** Spring Web
- Click **Generate**, unzip the file

### 2️⃣ Import into IntelliJ (or any IDE)

- Open IntelliJ IDEA  
- Go to `File > Open` → Select the project folder

### 3️⃣ Add RabbitMQ Dependency

In your `pom.xml`, add:

```xml
<dependency>
    <groupId>com.rabbitmq</groupId>
    <artifactId>amqp-client</artifactId>
    <version>5.25.0</version>
</dependency>
```

Also add:

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-amqp</artifactId>
</dependency>
```

---

## 📁 Project Structure

```
src/
├── main/
│   ├── java/
│   │   └── com.example.rabbitmqdemo/
│   │       ├── RabbitMqDemoApplication.java
│   │       ├── config/RabbitMQConfig.java
│   │       ├── controller/MessageController.java
│   │       ├── producer/MessageProducer.java
│   │       └── consumer/MessageConsumer.java
│   └── resources/
│       └── application.properties
```

---

## ⚙️ Configuration

### `application.properties`

```properties
# RabbitMQ Configuration
spring.rabbitmq.host=localhost
spring.rabbitmq.port=5672
spring.rabbitmq.username=guest
spring.rabbitmq.password=guest

# Queue name
rabbitmq.queue=my_queue
```

---

## 📤 Produce a Message

### Endpoint: `POST /produce`

Send a message using `curl`:

```bash
curl -X POST http://localhost:8080/produce \
-H "Content-Type: application/json" \
-d '{"message":"Hello from Producer!"}'
```

---

## 📥 Consume a Message

### Endpoint: `GET /consume`

Receive the message using:

```bash
curl http://localhost:8080/consume
```

---

## 📌 Notes

- Make sure RabbitMQ is running locally at `localhost:5672`  
- You can monitor messages via the RabbitMQ Management Dashboard (default: [http://localhost:15672](http://localhost:15672))  
  - Username: `guest`  
  - Password: `guest`

---

## 📚 References

- [Spring Boot AMQP Documentation](https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#messaging.amqp)
- [RabbitMQ Java Client](https://www.rabbitmq.com/java-client.html)
- [RabbitMQ Management Plugin](https://www.rabbitmq.com/management.html)

---

