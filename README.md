# 🐳 Docker
This repository contains my Docker learning notes, commands, and basic concepts.

## 📌 What is Docker?
Docker is a platform that allows us to build, package, and run applications inside lightweight and isolated containers.
A container contains an application and its required dependencies, making it easier to run the application consistently on different systems.

## 📦 Container:
A container is a lightweight and isolated environment in which an application runs with its dependencies.
Docker can run multiple containers on the same machine.

Example:

```text
Docker
│
├── Container 1 → Python App
├── Container 2 → Node.js App
└── Container 3 → Database
````

## 🖼️ Docker Image:
A Docker image is a blueprint used to create containers.

```text
Docker Image
     ↓
Docker Container
```
One image can be used to create multiple containers.

## ⚙️ Basic Docker Commands:

# Check Docker version
docker --version

# List images
docker images

# Download an image
docker pull <image_name>

# Run a container
docker run <image_name>

# Run container in background
docker run -d <image_name>

# List running containers
docker ps

# List all containers
docker ps -a

# Stop a container
docker stop <container_name>

# Start a container
docker start <container_name>

# Remove a container
docker rm <container_name>

# Remove an image
docker rmi <image_name>

# View container logs
docker logs <container_name>

## 🔌 Port Mapping:
Port mapping allows us to access an application running inside a container.

# docker run -p 8080:80 <image_name>
# Host Port : Container Port
    8080  :      80


## 🌐 Docker Networking:
Docker networks allow containers to communicate with each other.
# docker network ls
# docker network create mynetwork


Example:

```text
        Docker Network
        /            \
       /              \
   App Container   Database Container
```

## 📄 Dockerfile:
A Dockerfile contains instructions for building a Docker image.
Example:

```dockerfile
FROM python:3.12

WORKDIR /app

COPY . .

RUN pip install -r requirements.txt

EXPOSE 5000

CMD ["python", "app.py"]
```

Build the image:
# docker build -t my-app .

Run the container:
# docker run -p 5000:5000 my-app


## 🐳 Docker Compose:
Docker Compose is used to manage multiple containers/services together.
Example:

```yaml
services:
  app:
    image: my-app
    ports:
      - "5000:5000"

  database:
    image: mongo
```

# Start services:
docker compose up -d

Stop services:
```bash
docker compose down
```

## 💾 Docker Volumes
Volumes are used to store persistent data.
```bash
docker volume ls
docker volume create myvolume
```

Use a volume:
```bash
docker run --volume myvolume:/data <image_name>
```

## ☁️ Docker Hub
Docker Hub is used to store and share Docker images.
```bash
docker login
docker push username/image-name
docker pull username/image-name
```

## 🆚 Docker vs Virtual Machine:

| Docker Container      | Virtual Machine     |
| --------------------- | ------------------- |
| Lightweight           | Heavier             |
| Shares host OS kernel | Includes guest OS   |
| Starts quickly        | Usually slower      |
| Uses fewer resources  | Uses more resources |

## 📚 Topics Covered:
* Docker Basics
* Containers
* Docker Images
* Docker Commands
* Dockerfile
* Image Layers
* Port Mapping
* Environment Variables
* Docker Networking
* Docker Compose
* Docker Hub
* Docker Volumes
* Multi-Container Applications

## 🎯 Learning Goal:
My goal is to learn Docker and understand how to containerize applications, manage containers, work with multiple services, and prepare applications for deployment.

---
⭐ **Learning Docker | Software Engineering Student**

🐳 Build • Ship • Run

