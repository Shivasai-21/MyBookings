# MyBookings – Multi-Service Docker Setup

## 📌 Overview

**MyBookings** is a containerized multi-service booking platform built using Docker and Docker Compose.
The project includes separate services for:

* 🎬 Movie Booking
* 🚌 Bus Booking
* ✈️ Flight Booking
* 🚆 Train Booking

Each application runs independently inside its own Docker container, making the setup modular, scalable, and easy to manage.

---

## 🧱 Architecture

| Service        | Image Name    | Container Name    | Port      |
| -------------- | ------------- | ----------------- | --------- |
| Movie Booking  | `movieimage`  | `moviecontainer`  | `1111:80` |
| Bus Booking    | `busimage`    | `buscontainer`    | `2222:80` |
| Flight Booking | `flightimage` | `flightcontainer` | `3333:80` |
| Train Booking  | `trainimage`  | `traincontainer`  | `4444:80` |

---

## 🚀 Getting Started

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/Shivasai-21/MyBookings.git

cd MyBookings
```

---

### 2️⃣ Build Docker Images

Make sure Docker is installed and running before executing the following commands:

```bash
docker build -t movieimage ./movie

docker build -t busimage ./bus

docker build -t flightimage ./flight

docker build -t trainimage ./train
```

---

### 3️⃣ Start All Services

Launch all containers using Docker Compose:

```bash
docker compose up -d
```

---

## 🌐 Access the Applications

After the containers start successfully, access the services in your browser:

| Service           | URL                                            |
| ----------------- | ---------------------------------------------- |
| 🎬 Movie Booking  | [http://localhost:1111](http://localhost:1111) |
| 🚌 Bus Booking    | [http://localhost:2222](http://localhost:2222) |
| ✈️ Flight Booking | [http://localhost:3333](http://localhost:3333) |
| 🚆 Train Booking  | [http://localhost:4444](http://localhost:4444) |

---

## 🛠️ Useful Docker Commands

### Stop all services

```bash
docker compose down
```

### View running containers

```bash
docker ps
```

### Check container logs

```bash
docker logs <container_name>
```

Example:

```bash
docker logs moviecontainer
```

---

## 📂 Project Highlights

* Multi-container Dockerized setup
* Independent service architecture
* Simple static frontend applications
* Easy local deployment using Docker Compose
* Beginner-friendly microservice-style structure

---

## 📄 Notes

* `.gitignore` is configured to exclude:

  * cache files
  * system files
  * temporary files
  * secrets/environment files

* Ensure the following tools are installed:

  * Docker
  * Docker Compose

* This project can be extended further by integrating:

  * Databases (MySQL/PostgreSQL/MongoDB)
  * Reverse Proxy (Nginx)
  * CI/CD Pipelines (Jenkins/GitHub Actions)
  * Kubernetes deployment
  * Monitoring tools (Prometheus/Grafana)

---

## 👨‍💻 Author

Developed by **Shivasai-21**
DevOps Engineer | Docker & CI/CD Enthusiast
