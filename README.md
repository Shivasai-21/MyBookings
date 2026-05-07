# 🚀 MyBookings – Multi-Service Docker Booking Platform

MyBookings is a containerized multi-service booking platform built using **Docker** and **Docker Compose**.  
The project demonstrates how multiple independent applications can run inside isolated containers while being managed through a single orchestration setup.

---

# 📌 Overview

This project contains four independent booking services:

- 🎬 Movie Booking
- 🚌 Bus Booking
- ✈️ Flight Booking
- 🚆 Train Booking

Each service runs in its own Docker container, making the application modular, scalable, and easy to manage.

---

# 🧱 Architecture

| Service | Container Name | Port Mapping | Network |
|----------|----------------|--------------|----------|
| 🎬 Movie Booking | `moviecontainer` | `1111:80` | `movie_network` |
| 🚌 Bus Booking | `buscontainer` | `2222:80` | `bus_network`, `train_network` |
| ✈️ Flight Booking | `flightcontainer` | `3333:80` | `flight_network`, `movie_network` |
| 🚆 Train Booking | `traincontainer` | `4444:80` | `train_network`, `bus_network` |

---

# 📂 Project Structure

```bash
MyBookings/
│
├── movie/
│   ├── Dockerfile
│   └── index.html
│
├── bus/
│   ├── Dockerfile
│   └── index.html
│
├── flight/
│   ├── Dockerfile
│   └── index.html
│
├── train/
│   ├── Dockerfile
│   └── index.html
│
├── docker-compose.yml
├── README.md
└── .gitignore
```

---

# ⚙️ Technologies Used

- Docker
- Docker Compose
- HTML5
- CSS3
- Docker Networking
- Docker Volumes

---

# 🚀 Getting Started

## 1️⃣ Clone the Repository

```bash
git clone https://github.com/Shivasai-21/MyBookings.git

cd MyBookings
```

---

## 2️⃣ Build Docker Images

Make sure Docker is installed and running before executing the following commands.

```bash
docker build -t movieimage ./movie

docker build -t busimage ./bus

docker build -t flightimage ./flight

docker build -t trainimage ./train
```

---

## 3️⃣ Start All Services

Launch all containers using Docker Compose.

```bash
docker compose up -d
```

---

# 🌐 Access the Applications

After the containers start successfully, access the applications in your browser.

| Service | URL |
|----------|------|
| 🎬 Movie Booking | http://localhost:1111 |
| 🚌 Bus Booking | http://localhost:2222 |
| ✈️ Flight Booking | http://localhost:3333 |
| 🚆 Train Booking | http://localhost:4444 |

---

# 🐳 Docker Compose Configuration

```yaml
version: "3.8"

services:
  movie:
    container_name: moviecontainer
    build: ./movie/
    ports:
      - "1111:80"
    networks:
      - movie_network
    volumes:
      - movie:/opt/movievolume01

  bus:
    container_name: buscontainer
    build: ./bus/
    ports:
      - "2222:80"
    networks:
      - bus_network
      - train_network
    volumes:
      - bus:/opt/busvolume01

  flight:
    container_name: flightcontainer
    build: ./flight/
    ports:
      - "3333:80"
    networks:
      - flight_network
      - movie_network

  train:
    container_name: traincontainer
    build: ./train/
    ports:
      - "4444:80"
    networks:
      - train_network
      - bus_network

networks:
  flight_network:
    driver: bridge

  bus_network:
    driver: bridge

  train_network:
    driver: bridge

  movie_network:
    driver: bridge

volumes:
  movie:
  bus:
```

---

# 🔗 Docker Networking

This project uses custom Docker bridge networks to simulate communication between services.

## Networks Used

- `movie_network`
- `bus_network`
- `train_network`
- `flight_network`

## Shared Communication

- Bus and Train services communicate through `train_network`
- Flight and Movie services communicate through `movie_network`

This setup demonstrates a beginner-friendly microservice networking architecture.

---

# 💾 Docker Volumes

Persistent volumes are attached for selected services.

| Service | Volume |
|----------|---------|
| Movie Service | `movie` |
| Bus Service | `bus` |

Volumes help preserve data even after containers are removed.

---

# 🛠️ Useful Docker Commands

## Stop All Containers

```bash
docker compose down
```

## View Running Containers

```bash
docker ps
```

## View Container Logs

```bash
docker logs <container_name>
```

### Example

```bash
docker logs moviecontainer
```

---

# 📌 Project Highlights

- Multi-container Dockerized setup
- Independent service architecture
- Custom bridge networking
- Persistent storage using Docker volumes
- Simple static frontend applications
- Easy local deployment using Docker Compose
- Scalable and modular project structure

---

# 📄 .gitignore Configuration

The `.gitignore` file excludes unnecessary files such as:

- Cache files
- Temporary files
- System-generated files
- Environment files
- Secret configurations

---

# 🔮 Future Enhancements

This project can be extended further by integrating:

- MySQL / PostgreSQL / MongoDB
- Nginx Reverse Proxy
- Jenkins CI/CD Pipeline
- GitHub Actions
- Kubernetes Deployment
- Prometheus & Grafana Monitoring
- Load Balancing
- Service Discovery

---

# ✅ Prerequisites

Ensure the following tools are installed:

- Docker
- Docker Compose
- Git

---

# 👨‍💻 Author

### Shivasai-21

DevOps Enthusiast | Docker | CI/CD | Kubernetes | Cloud & Automation

🔗 GitHub:  
https://github.com/Shivasai-21

---

# ⭐ Support

If you found this project useful, consider giving it a ⭐ on GitHub.
