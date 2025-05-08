# HelloApp - Spring Boot + Docker

This is a basic Spring Boot application that demonstrates how to build a simple REST endpoint, containerize it using Docker, and deploy it using an OpenJDK base image.

## Features

- Accepts a name in the URL path and responds with `Hello <name>`.
- Dockerized using a custom `Dockerfile`.
- Pushed to Docker Hub for easy deployment.

## Endpoint

GET /hello/{name}

**Example:**

http://localhost:8080/hello/Tanay

**Response:**

Hello Tanay

---

## Prerequisites

- Java 17+
- Docker
- Git
- Maven (if building locally)

---

## Running Locally (Without Docker)

```bash
./mvnw spring-boot:run
Then visit: http://localhost:8080/hello/YourName

Docker Setup
Step 1: Build Docker Image
bash
docker build -t your-dockerhub-username/helloapp .

Step 2: Push to Docker Hub
bash
docker push your-dockerhub-username/helloapp
Step 3: Run Docker Container
bash
docker run -p 8080:8080 your-dockerhub-username/helloapp
Then open: http://localhost:8080/hello/YourName

Dockerfile Example
Dockerfile
FROM openjdk:17
COPY target/helloapp-0.0.1-SNAPSHOT.jar helloapp.jar
ENTRYPOINT ["java", "-jar", "helloapp.jar"]
Repository Structure
.
├── src
├── target
├── Dockerfile
├── pom.xml
└── README.md

Author: Tanay
Docker Hub: [tanayvj]
````
---

## License
This project is open source and available under the MIT License.
