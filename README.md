# DevOps Deployment for Ollama Service

## Introduction
This repository contains the DevOps deployment for the Ollama service. The Ollama service is a simple web application that allows users to upload images and get a llama-fied version of the image. The service is built using Spring Boot Microservice (SBMS) and is deployed using Docker and Kubernetes.

## Setup Docker
To setup the docker, follow the steps below:
1. Install Docker Desktop
2. Run command `docker-compose up -d` to start the docker container
   - `docker` folder contains the configuration files for the docker container incldue prometheus, grafana, etc.
3. Run command `docker ps` to check the running containers

## Setup Kubernetes
To setup the kubernetes, see [README](k8s/README.md) file in the k8s directory.

## Setup Jenkins
To setup the Jenkins, see [README](jenkins/README.md) file in the jenkins directory.

## Brief Container Details
- **postgres**: Database for all services, port 5432 for connection
- **rabbitmq**: Message broker for the Auth and Mail services, port 5672 for connection, 15672 for management
- **zookeeper**: Centralized service for maintaining configuration information of Kafka broker, port 2181 for connection
- **broker**: Kafka message broker for the Chat and Notification services, port 9092, 29092 for internal communication
- **schema-registry**: Centralized service for maintaining Avro schemas, port 8081 -> 8085
- **kafka-ui**: Web UI tool for Kafka, port 8880 -> 8086
- **redis**: Cache for the Gateway and Auth services, port 6379
- **loki**: Log aggregation system, port 3100 for connection
- **tempo**: Distributed tracing system, port 3100 -> 3110, 9411 for zipkin
- **prometheus**: Monitoring system, port 9090 for connection
- **grafana**: Visualization tool for Prometheus, port 3000 -> 3300, Use Dashboard ID: 19964 for Spring Boot Stats
- **alertmanager**: Alerting system for Prometheus, port 9093 for connection