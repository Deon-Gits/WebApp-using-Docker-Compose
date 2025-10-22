🐳 **Dockerized Web Application Using Docker Compose**

📌 Overview

This project demonstrates how to set up a containerized development environment using Docker Compose following a microservices architecture.
It consists of two main services:

PHP & Apache Web Server

MySQL Database Server

The connection between the PHP application and the database is established using the MySQLi module.

⚙️ What is Docker Compose?

Docker Compose is a tool that allows you to define and run multi-container Docker applications.
With a single YAML file (docker-compose.yml), you can configure services, networks, and volumes—eliminating the need to manually start multiple containers.

Originally intended for development and testing, Docker Compose is now also used to deploy services in a Docker Swarm environment.

🧩 What Are Microservices?

Microservices is an architectural style that breaks an application into small, independent services.
Each service focuses on a specific business function and can be developed, deployed, and scaled independently—unlike monolithic applications.

📁 Project Structure
.
├── docker-compose.yml
├── php/
│   ├── Dockerfile
│   └── index.php
└── mysql/ (if configured for persistence or custom scripts)

🛠️ Services Defined in docker-compose.yml
✅ 1. Web Service (php)

Uses the php:7.3.3-apache image.

Mounts local php/ directory into the container using a volume.

Serves the application via Apache on port 80 (mapped to host port 8000).

Contains index.php which checks the database connection.

✅ 2. Database Service (mysql)

Uses the mysql:8.0 image.

Configured to use native password authentication.

Environment variables define MySQL credentials.

Exposes MySQL ports 3306 and 6033.

Dockerfile installs required PHP modules like mysqli.

▶️ How to Run the Project Locally
1. Clone the Repository
git clone https://github.com/mtliba/Creating-a-Containerized-Web-Application-with-docker-compose.git
cd Creating-a-Containerized-Web-Application-with-docker-compose

2. Build and Start Containers
docker-compose up --build

3. Access the Application

Open your browser and go to:

http://localhost:8000

⏹️ How to Stop and Manage Containers
Action	Command
Stop all services	docker-compose down
List Docker images	docker image ls
List all containers	docker container ls -a
✅ Result

Once running, the PHP application will attempt to connect to the MySQL database and display a success or failure message based on the connection status.
