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

## 🔧 Environment & Tools
* **Host**: AWS EC2 Instance.
* **OS**: Ubuntu 24.04 LTS.
* **Container Runtime**: Docker Engine.
