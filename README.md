# MyBookings – Multi‑Service Docker Setup

## 📌 Overview
This repository contains a simple booking system composed of multiple services:
- **Movie Service** (`movieimage`)
- **Bus Service** (`busimage`)
- **Flight Service** (`flightimage`)
- **Train Service** (`trainimage`)

Each service runs in its own Docker container and is orchestrated using **Docker Compose**.


## 🚀 Getting Started

**1. Clone the repository**
git clone https://github.com/Shivasai-21/MyBookings.git
cd MyBookings

**2. Build the images**
Make sure Docker is running, then build each service image:

bash
docker build -t movieimage ./movie
docker build -t busimage ./bus
docker build -t flightimage ./flight
docker build -t trainimage ./train
3. Start the services
Use Docker Compose to bring everything up:

bash
docker compose up -d

**🔌 Ports**
Each service is mapped to a unique port:

Service	Container Name	Image	Port Mapping
Movie	moviecontainer	movieimage	1111:80
Bus	buscontainer	busimage	2222:80
Flight	flightcontainer	flightimage	3333:80
Train	traincontainer	trainimage	4444:80


**Access them via:**

Movie → http://localhost:1111

Bus → http://localhost:2222

Flight → http://localhost:3333

Train → http://localhost:4444

**🛠️ Useful Commands**
Stop all services:

**bash**
docker compose down
View running containers:

**bash**
docker ps
Check logs for a specific service:

**bash**
docker logs <container_name>

**📄 Notes**
.gitignore is configured to exclude system files, caches, and secrets.

Ensure you have Docker and Docker Compose installed before running.

You can extend this setup by adding databases, reverse proxies (like Nginx), or CI/CD pipelines.

**👨‍💻 Author**
Developed by Shivasai-21  
DevOps Engineer | Docker & CI/CD Enthusiast
