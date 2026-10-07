# Dockerized Python Flask Application

## 📌 Experiment Overview

This experiment demonstrates how to **containerize a Python Flask web application using Docker**.

A simple Flask application is created, packaged into a Docker image using a `Dockerfile`, and executed inside a Docker container. The application is exposed on port `5000` and accessed through a web browser using `http://localhost:5000`.

This experiment demonstrates the basic workflow of:

**Python Application → Dockerfile → Docker Image → Docker Container → Web Browser**

> **Note:** This experiment is performed locally using Docker Desktop. It demonstrates containerization and local deployment rather than deployment to a public cloud platform.

---

## 🎯 Objectives

The main objectives of this experiment are:

- To verify the installation and working of Docker.
- To understand the concept of Docker images and containers.
- To create a simple Python Flask web application.
- To define Python dependencies using `requirements.txt`.
- To create a Docker image using a `Dockerfile`.
- To build and verify a Docker image.
- To run the application inside a Docker container.
- To map the container port to the host system.
- To access the containerized Flask application through a web browser.
- To understand the basic workflow of application containerization.

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Application programming language |
| Flask | Python web framework |
| Docker | Containerization platform |
| Docker Desktop | Local Docker environment |
| Dockerfile | Defines Docker image configuration |
| PowerShell | Command-line execution |
| Web Browser | Accessing the Flask application |
| Python 3.12 Slim | Base Docker image |

---

## 🏗️ Architecture

The application follows the following architecture:

```text
Web Browser
     │
     │ http://localhost:5000
     ▼
Windows Host
     │
     │ Port Mapping: 5000:5000
     ▼
Docker Container
     │
     ▼
Flask Application
     │
     ▼
Python 3.12
