# 🐳 Docker & Kubernetes ITI Labs

This repository contains practical implementations for Docker and Kubernetes labs performed on an **AWS EC2 (Ubuntu 24.04)** instance.

---

## 🛠 Lab 1: Docker Fundamentals & Resource Limits
This lab focused on basic container management and implementing hardware constraints.

### Key Tasks:
* **Image Operations**: Pulling and running lightweight images like `nginx:alpine`.
* **Resource Constraints**: Implementing **Memory Limits** using the `--memory` flag to optimize host performance.
* **CLI Proficiency**: Managing container lifecycles (run, stop, rm) and inspecting container status.

---

## 🚀 Lab 2: Networking, Volumes, and Dockerization
This lab covered building custom images, advanced networking, and persistent storage.

### 1. Dockerizing a Python Flask App
* **Base Image**: Used **Alpine Linux** for a minimal footprint.
* **Customization**: Manually installed `python3` and `py3-pip` and managed dependencies.
* **Registry**: Published the final image to **Docker Hub**.

### 2. Custom Networking (Bridge)
* **Creation**: Built a custom network named `iti-network`.
* **Subnetting**: Configured a specific subnet `10.0.0.0/8` for the internal network.

### 3. Volumes & Port Mapping
* **Bind Mounts**: Used **Volumes** to link a local `index.html` file to the container's web directory.
* **Port Publishing**: Mapped container port **8080** to host port **8080** for external access.

---

# Docker Lab #3: Private Registry, WordPress, and Reverse Proxy

## 📝 Overview
This lab focuses on advanced Docker concepts including:
* **Running a Private Insecure Registry.**
* **Custom Image building** and tagging for private distribution.
* **Multi-service orchestration** using Docker Compose.
* **Implementing a Reverse Proxy** with Nginx to serve a Flask application.

---

## 🛠 Environment & Tools
* **Host:** AWS EC2 Instance.
* **OS:** Ubuntu 24.04 LTS.
* **Container Runtime:** Docker Engine.

---

## 🚀 Lab Parts

### Part 1: Private Insecure Registry
In this section, a local registry was deployed to host private images.
* **Deploy Registry:** Started the CNCF distribution registry on port `5000`.
* **Configuration:** Configured the Docker daemon (`daemon.json`) to allow insecure communication with `localhost:5000`.
* **Custom Nginx:** * Built a custom image based on `alpine:latest`.
    * Tagged as `localhost:5000/my-custom-nginx:v1`.
    * Pushed to the local registry.

### Part 2: WordPress & MySQL Deployment
A multi-container environment was set up using Docker Compose.
* **Database:** `mysql:5.7` with persistent data mounted to the host path `./mysql_data`.
* **Application:** `wordpress:latest` exposed on port `8080`.
* **Networking:** Automatic service discovery between the WordPress and MySQL containers.

### Part 3: Flask App with Nginx Reverse Proxy (Bonus)
Integrating the Flask application developed in **Lab 2**.
* [cite_start]**Image Migration:** The image `abdelrahimbebo/iti-flask-lab2` was pulled and re-tagged for the private registry[cite: 87, 121].
* **New Tag:** `localhost:5000/my-flask-app:v1`.
* **Architecture:**
    * **Flask Service:** Running the application logic.
    * **Nginx Service:** Acting as a reverse proxy, listening on port `80` and forwarding requests to the Flask container.
    * **Registry Integration:** The Compose file pulls the Flask image directly from the local private registry.

---
