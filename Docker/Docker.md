# 🐳 Docker Learning Journey

## 📅 Date
17 July 2026

---

# 📖 About Docker

Docker is an open-source platform used to build, package, ship, and run applications inside lightweight containers.

Instead of installing software directly on the operating system, Docker packages everything the application needs, including libraries, dependencies, and runtime.

This ensures that applications work consistently across development, testing, and production environments.

---

# 🚀 Why Docker?

- Lightweight
- Fast startup
- Portable
- Consistent environment
- Easy deployment
- Isolation between applications
- Better resource utilization

---

# 🏗 Docker Architecture

Docker Client
        │
        ▼
Docker Engine (Docker Daemon)
        │
 ┌──────┴──────┐
 │             │
Images     Containers
        │
Docker Hub

---

# 📦 Docker Components

## Docker Engine

Runs Docker services.

## Docker Image

Blueprint used to create containers.

Example:

ubuntu

nginx

node

mysql

---

## Docker Container

Running instance of an image.

Multiple containers can be created from one image.

---

## Docker Hub

Cloud repository where Docker images are stored.

---

# 📝 Commands Learned

## Check Docker Version

```bash
docker --version
```

## List Images

```bash
docker images
```

## Download Image

```bash
docker pull nginx
```

## Run Container

```bash
docker run nginx
```

## Run Container in Background

```bash
docker run -d nginx
```

## Port Mapping

```bash
docker run -d -p 8080:80 nginx
```

Host Port → Container Port

---

## Running Containers

```bash
docker ps
```

All Containers

```bash
docker ps -a
```

---

## Stop Container

```bash
docker stop <container_id>
```

---

## Start Container

```bash
docker start <container_id>
```

---

## Restart Container

```bash
docker restart <container_id>
```

---

## Remove Container

```bash
docker rm <container_id>
```

---

## Remove Image

```bash
docker rmi <image_id>
```

---

# 📄 Dockerfile

Dockerfile is a text file that contains instructions to build a Docker Image.

Example:

```dockerfile
FROM nginx
COPY . /usr/share/nginx/html
```

---

# 🌐 Port Mapping

```text
Host Machine
localhost:8080
        │
        ▼
Docker Container
Port 80
```

Example:

```bash
docker run -d -p 8080:80 nginx
```

Opening

```
http://localhost:8080
```

loads the Nginx web page.

---

# 🌍 Nginx

Nginx is a high-performance Web Server and Reverse Proxy Server.

Docker is commonly used to run Nginx containers for hosting websites.

---

# 📚 What I Learned

- Docker Basics
- Docker Architecture
- Docker Engine
- Docker Images
- Docker Containers
- Docker Hub
- Docker Installation
- Docker Commands
- Dockerfile
- Port Mapping
- Nginx Basics

---

# 📸 Practice Screenshots

Add screenshots inside the images folder.

- Docker Installation
- Docker Version
- Docker Images
- Docker Pull
- Docker Run
- Docker PS
- Docker Stop
- Docker Remove Container
- Docker Remove Image
- Port Mapping
- Nginx Running

---

# 🎯 Outcome

Successfully learned Docker fundamentals, container lifecycle, Docker images, Docker Hub, Dockerfile basics, Nginx deployment, and port mapping through hands-on practice.

---
