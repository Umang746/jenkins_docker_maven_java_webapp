# Jenkins Pipeline for Dockerized Java Web App

![Jenkins](https://img.shields.io/badge/Jenkins-CI/CD-yellow?style=for-the-badge&logo=jenkins)
![Docker](https://img.shields.io/badge/Docker-Containerization-blue?style=for-the-badge&logo=docker)
![Maven](https://img.shields.io/badge/Maven-Build%20Tool-orange?style=for-the-badge&logo=apache-maven)
![Java](https://img.shields.io/badge/Java-Programming-yellow?style=for-the-badge&logo=java)

This project utilizes Jenkins pipeline for end-to-end CI/CD, Docker for containerization, Maven for building Java applications, and Java for the web application. The CI/CD pipeline involves multiple operating systems for Jenkins master, Jenkins slave, QA testing, and production deployment.

## Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Project Structure](#project-structure)
- [Jenkins Pipeline](#jenkins-pipeline)
- [Usage](#usage)


## Overview

The purpose of this project is to showcase an end-to-end CI/CD pipeline using Jenkins, Docker, Maven, and Java for a web application. The pipeline involves multiple operating systems, with Jenkins orchestrating the entire process from code push to production deployment.

## Prerequisites

Ensure you have the following prerequisites before setting up the pipeline:

- Jenkins installed and configured on the master and slave nodes.
- Docker installed on all nodes.
- Maven installed on the Jenkins slave node.
- Java installed on the Jenkins slave node.
- SSH connectivity between Jenkins nodes and QA/Production nodes.

## Project Structure

```plaintext
jenkins_docker_maven_java_webapp/
│
├── src/
│   └── ... (Java web app source code)
│
├── Dockerfile
├── Jenkinsfile
├── ...
│
└── README.md
```

- `src/`: Contains the source code for the Java web application.
- `Dockerfile`: Defines the Docker image for the web application.
- `Jenkinsfile`: Jenkins pipeline script defining the CI/CD process.
- `README.md`: Project documentation.

## Jenkins Pipeline

The Jenkins pipeline consists of the following stages:

1. **Code Pull and Build:**

-  Jenkins master triggers a pipeline on code push.
-  Jenkins slave pulls the code and builds the Java web application.
-  Docker image is created with the web app and pushed to the Docker registry.

2. **QA Testing:**

- Jenkins contacts the QA team's operating system via SSH.
- If QA approves, the pipeline proceeds to the next stage.

3. **Production Deployment:**

- Jenkins contacts the production environment via SSH.
- Deploy the latest Dockerized Java web application.

## Usage
1.**Setup Jenkins:**
- Install and configure Jenkins on the master and slave nodes.

2.**Configure Jenkins Pipeline:**
- Create a new pipeline job in Jenkins and link it to the Jenkinsfile.

3.**Run the Pipeline:**
- Trigger the pipeline manually or on code push events.

4.**Monitor and Review:**
- Monitor the Jenkins console for pipeline progress and review the logs.
