# 🐳 Day 2 - Docker Commands & Intermediate Concepts

**Date:** 16 July 2026

---

# 📖 Topics Covered

* Docker Commands
* Dockerfile
* Dockerfile Instructions
* Docker Volumes
* Docker Networks
* Docker Compose
* Docker Mini Project Workflow
* Docker Interview Questions
* Docker MCQ Assessment

---

# 🖥 Docker Commands

## 1. `docker --version`

Displays the installed Docker version.

```bash
docker --version
```

---

## 2. `docker info`

Displays detailed information about Docker.

```bash
docker info
```

Shows:

* Docker Version
* Number of Images
* Number of Containers
* CPU
* Memory
* Storage Driver
* Docker Root Directory

---

## 3. `docker images`

Lists all Docker Images stored on the local machine.

```bash
docker images
```

---

## 4. `docker ps`

Displays only running containers.

```bash
docker ps
```

---

## 5. `docker ps -a`

Displays all containers (Running + Stopped).

```bash
docker ps -a
```

---

## 6. `docker pull`

Downloads an image from Docker Hub.

```bash
docker pull nginx
```

---

## 7. `docker run`

Creates and starts a new container.

```bash
docker run nginx
```

### Internal Workflow

```
docker run nginx
        │
        ▼
Check Local Image
        │
Image Available?
     /       \
   Yes       No
    │         │
    │   Download Image
    │         │
    └─────────┘
        │
Create Container
        │
Start Container
```

---

## 8. `docker start`

Starts an existing stopped container.

```bash
docker start my-nginx
```

---

## 9. `docker stop`

Stops a running container.

```bash
docker stop my-nginx
```

---

## 10. `docker restart`

Stops and starts the container again.

```bash
docker restart my-nginx
```

---

## 11. `docker rm`

Removes a container.

```bash
docker rm my-nginx
```

---

## 12. `docker rmi`

Removes a Docker Image.

```bash
docker rmi nginx
```

---

## 13. `docker exec`

Executes commands inside a running container.

```bash
docker exec -it my-nginx bash
```

---

## 14. `docker logs`

Displays container logs.

```bash
docker logs my-nginx
```

---

## 15. `docker inspect`

Displays detailed information about a container or image.

```bash
docker inspect my-nginx
```

---

## 16. `docker build`

Builds a Docker Image from a Dockerfile.

```bash
docker build -t myapp .
```

---

## 17. `docker tag`

Creates a new tag for an image.

```bash
docker tag myapp myapp:v1
```

---

## 18. `docker push`

Uploads an image to Docker Hub.

```bash
docker push username/myapp:v1
```

---

# 📝 Dockerfile

A **Dockerfile** is a text file that contains instructions to automatically build a Docker Image.

---

## Dockerfile Workflow

```
Application Code
        │
        ▼
Dockerfile
        │
docker build
        │
        ▼
Docker Image
        │
docker run
        │
        ▼
Docker Container
```

---

## Dockerfile Example

```dockerfile
FROM node:20

WORKDIR /app

COPY . .

RUN npm install

ENV PORT=3000

EXPOSE 3000

CMD ["npm","start"]
```

---

# 📚 Dockerfile Instructions

## FROM

Specifies the base image.

```dockerfile
FROM node:20
```

---

## WORKDIR

Sets the working directory.

```dockerfile
WORKDIR /app
```

---

## COPY

Copies files into the Docker Image.

```dockerfile
COPY . .
```

---

## RUN

Executes commands during image build.

```dockerfile
RUN npm install
```

---

## ENV

Defines environment variables.

```dockerfile
ENV PORT=3000
```

---

## EXPOSE

Specifies the application port.

```dockerfile
EXPOSE 3000
```

> **Note:** `EXPOSE` only documents the listening port. To access the application from outside the container, use port mapping with `-p`.

---

## CMD

Defines the default command executed when the container starts.

```dockerfile
CMD ["npm","start"]
```

---

## ENTRYPOINT

Defines the fixed executable that always runs when the container starts.

Example:

```dockerfile
ENTRYPOINT ["python"]

CMD ["app.py"]
```

Executes:

```
python app.py
```

---

# ⚖ RUN vs CMD

| RUN                            | CMD                                  |
| ------------------------------ | ------------------------------------ |
| Executes during `docker build` | Executes during `docker run`         |
| Used while building the image  | Starts the application               |
| Runs only once during build    | Runs every time the container starts |

---

# 📦 Docker Volumes

Docker Volumes are used to store persistent data outside the container.

---

## Why Volumes?

Without Volume

```
Container
     │
Save Data
     │
Container Deleted
     │
❌ Data Lost
```

With Volume

```
Container
     │
Save Data
     │
Docker Volume
     │
Container Deleted
     │
✅ Data Safe
```

---

## Create Volume

```bash
docker volume create mydata
```

---

## List Volumes

```bash
docker volume ls
```

---

## Attach Volume

```bash
docker run -v mydata:/app nginx
```

---

## Remove Volume

```bash
docker volume rm mydata
```

---

## Types of Storage

### Named Volume

```bash
docker volume create mydata
```

---

### Anonymous Volume

```bash
docker run -v /app nginx
```

---

### Bind Mount

```bash
docker run -v C:\Projects:/app nginx
```

---

# 🌐 Docker Networks

Docker Networks allow communication between containers.

---

## Why Networks?

```
React Container
        │
        ▼
Docker Network
        ▲
        │
ASP.NET Core API
        │
        ▼
MongoDB Container
```

---

## Types of Docker Networks

* Bridge (Default)
* Host
* None
* Overlay

---

## Create Network

```bash
docker network create mynetwork
```

---

## List Networks

```bash
docker network ls
```

---

## Inspect Network

```bash
docker network inspect mynetwork
```

---

## Remove Network

```bash
docker network rm mynetwork
```

---

## Run Container in Network

```bash
docker run --network mynetwork nginx
```

---

# 🐳 Docker Compose

Docker Compose is used to manage multiple containers using a single YAML configuration file.

---

## Docker Compose Workflow

```
docker-compose.yml
        │
        ▼
docker compose up
        │
        ▼
React Container
        │
ASP.NET Core API
        │
MongoDB Container
        │
Automatic Network
        │
Automatic Volumes
        ▼
Application Running
```

---

## Docker Compose File

```yaml
version: "3.9"

services:

  frontend:
    image: react-app

  api:
    image: visitor-api

  mongodb:
    image: mongo
```

---

## Commands

Start all services

```bash
docker compose up
```

Background mode

```bash
docker compose up -d
```

Stop all services

```bash
docker compose down
```

View logs

```bash
docker compose logs
```

---

# 📊 Docker vs Docker Compose

| Docker                         | Docker Compose                     |
| ------------------------------ | ---------------------------------- |
| Single Container               | Multiple Containers                |
| Multiple `docker run` commands | Single `docker compose up` command |
| Manual networking              | Automatic networking               |
| Manual startup                 | Automatic startup                  |

---

# 🎯 Important Interview Questions

1. What is Docker?
2. Why Docker?
3. What is a Docker Image?
4. What is a Docker Container?
5. Difference between Docker Image and Container.
6. Difference between Docker and Virtual Machine.
7. Explain Docker Architecture.
8. Explain Docker Workflow.
9. What happens when `docker run nginx` is executed?
10. Difference between `docker pull` and `docker run`.
11. Difference between `docker run` and `docker start`.
12. Difference between `RUN` and `CMD`.
13. Difference between `CMD` and `ENTRYPOINT`.
14. What is Dockerfile?
15. Why Docker Volumes?
16. Why Docker Networks?
17. What is Docker Compose?
18. Difference between Docker and Docker Compose.

---

# 📝 Final Assessment

### Docker Final MCQ Score

✅ **19 / 20 (95%)**

---

# 📚 Learning Summary

Today I learned Docker Commands, Dockerfile, Dockerfile Instructions, Docker Volumes, Docker Networks, Docker Compose, and the complete workflow of containerizing multi-container applications. I also practiced interview questions, understood real-world Docker architecture, and completed the Docker Final MCQ Assessment with a score of **19/20 (95%)**. Tomorrow, I will implement these concepts practically by creating Dockerfiles, Docker Compose configurations, running containers, and documenting the results with screenshots.
