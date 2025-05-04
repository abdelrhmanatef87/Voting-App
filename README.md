# Example Voting App - Dockerized

This repository contains a **voting app** that I have Dockerized using **Dockerfiles** for each component and orchestrated using **Docker Compose**. The app consists of multiple services running in separate containers, including the voting frontend, results frontend, Redis for message queuing, and Postgres for storing votes. Below are the exact components I created and configured.

## 🛠️ What I Built

### 1. **Dockerfiles for the Application Components**
I created **3 Dockerfiles** for the main application components:
- **Vote App** (Frontend): A Python-based web app where users can vote between two options.
- **Result App** (Frontend): A Node.js-based web app that displays the voting results.
- **Worker**: A .NET-based service that consumes votes and stores them in a Postgres database.

Each of these Dockerfiles defines how to build the respective service, including the base images, dependencies, and configurations needed to run the services inside their respective containers.

### 2. **Docker Compose Setup**
I created a **Docker Compose** configuration file to manage the multi-container application. This file orchestrates the deployment of all the services:
- **Vote App** (Python)
- **Result App** (Node.js)
- **Redis** (Message Queue)
- **Postgres** (Database)
- **Worker** (.NET)

The **Docker Compose** file allows all services to be built and run together in a single command, simplifying the process of managing multiple containers.

### 3. **Service Interactions**
I configured the following interactions between the services:
- **Vote App** communicates with **Postgres** for storing votes.
- **Result App** fetches voting results from **Postgres**.
- **Redis** is used as a message queue to pass votes between the services.
- **Worker** processes the votes and stores them in the database.

### 4. **Ports and Networking**
The services are configured to run on different ports and communicate through the Docker network. Specifically:
- **Vote App** runs on port `8080`
- **Result App** runs on port `8081`
- **Postgres** and **Redis** run internally without exposed ports.

## 🚀 Getting Started

To get the app running on your local machine, follow these steps:

### 1. Clone the Repository
```bash
git clone https://github.com/abdelrhmanatef87/example-voting-app.git
cd example-voting-app
