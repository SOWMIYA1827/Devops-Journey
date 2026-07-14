# 🐳 Day 1 - Docker Fundamentals

**Date:** 14 July 2026

## 📖 Topics Covered

- What is Docker?
- Why Docker?
- Problems Docker Solves
- Docker Image
- Docker Container
- Docker Hub
- Docker Architecture
- Docker Client
- Docker Daemon
- Image vs Container
- Virtual Machine vs Docker
- Docker Workflow

---

## 🧠 Key Concepts

### What is Docker?

Docker is an open-source platform that packages an application along with its dependencies, libraries, runtime, and configuration into a container. This ensures the application runs consistently across different environments.

---

### Why Docker?

Without Docker:
- Dependency mismatch
- Environment issues
- Deployment failures
- Version conflicts

With Docker:
- Consistent environment
- Faster deployment
- Lightweight containers
- Easy scalability
- Portable applications

---

---

## 🖼 What is a Docker Image?

A **Docker Image** is a **read-only blueprint or template** used to create Docker Containers. It contains everything an application needs to run, including the application code, runtime, libraries, dependencies, and configuration files.

### 📌 Docker Image Contains

- Application Code
- Runtime
- Libraries
- Dependencies
- Configuration Files

### ✅ Key Features

- Read-only template
- Cannot execute by itself
- Used to create Docker Containers
- One Docker Image can create multiple Docker Containers
- Portable and easy to share through Docker Hub

### 📊 Example

```
Docker Image
     │
     ├── Container 1
     ├── Container 2
     ├── Container 3
     └── Container 4
```

**Real-Life Analogy:**

- **Docker Image** → Cake Recipe 📖
- **Docker Container** → Baked Cake 🎂

The recipe (Image) is used to make many cakes (Containers), but the recipe itself cannot be eaten or executed.

---

## 💻 Virtual Machine vs Docker

A **Virtual Machine (VM)** is a virtualization technology that runs a complete Guest Operating System on top of a Hypervisor. Each Virtual Machine has its own Operating System, making it larger in size and consuming more system resources.

**Docker** is a containerization platform that packages applications and their dependencies into lightweight containers. Unlike Virtual Machines, Docker Containers share the Host Operating System kernel, making them faster and more efficient.

### 📊 Comparison

| Virtual Machine | Docker |
|-----------------|--------|
| Uses a Hypervisor | Uses Docker Engine |
| Runs a complete Guest Operating System | Shares the Host Operating System Kernel |
| Heavyweight | Lightweight |
| Requires more CPU and RAM | Requires less CPU and RAM |
| Takes minutes to start | Starts in seconds |
| Large storage size | Small storage size |
| Lower resource efficiency | Higher resource efficiency |
| Better for running multiple operating systems | Better for deploying applications |

### 🏗 Architecture

#### Virtual Machine

```
+---------------------------+
|      Applications         |
+---------------------------+
|       Guest OS            |
+---------------------------+
|       Hypervisor          |
+---------------------------+
|        Host OS            |
+---------------------------+
|        Hardware           |
+---------------------------+
```

#### Docker

```
+---------------------------+
|      Applications         |
+---------------------------+
|      Docker Container     |
+---------------------------+
|      Docker Engine        |
+---------------------------+
|        Host OS            |
+---------------------------+
|        Hardware           |
+---------------------------+
```

### 🍕 Real-Life Analogy

**Virtual Machine 🏠**
- Every family gets a separate house.
- Each house has its own kitchen, bathroom, electricity, and water connection.
- More space and higher maintenance.

**Docker Container 🏢**
- Multiple families live in the same apartment building.
- They share the building infrastructure but have separate apartments.
- Less space, lower cost, and faster to manage.

### 🎯 Key Takeaway

- **Virtual Machines** provide complete operating system isolation but consume more resources.
- **Docker Containers** share the Host OS kernel, making them lightweight, faster to start, and ideal for modern application deployment.

## 🖼 Docker Workflow

```
Developer
    │
    ▼
Create Docker Image
    │
    ▼
Push to Docker Hub
    │
    ▼
Pull Image
    │
    ▼
Run Docker Container
```

---

## 🏗 Docker Architecture

```
Developer
    │
    ▼
Docker Client
    │
    ▼
Docker Daemon
    │
    ▼
Docker Image
    │
    ▼
Docker Container
```

### Components

### Docker Client
- Accepts Docker commands.
- Example:
  - `docker run`
  - `docker pull`
  - `docker ps`

### Docker Daemon
Performs the actual Docker operations:
- Pull Images
- Build Images
- Create Containers
- Start Containers
- Stop Containers
- Remove Containers

### Docker Image
- Read-only blueprint.
- Contains:
  - Application Code
  - Runtime
  - Libraries
  - Dependencies
  - Configuration

### Docker Container
- Running instance of a Docker Image.
- Executes the application.

---

## 📦 Docker Image vs Docker Container

| Docker Image | Docker Container |
|--------------|------------------|
| Blueprint | Running Instance |
| Read-only | Running Application |
| Cannot execute itself | Executes the application |
| Used to create containers | Created from an image |

---

## 💻 Virtual Machine vs Docker

| Virtual Machine | Docker |
|-----------------|--------|
| Full Guest OS | Shares Host OS Kernel |
| Heavy | Lightweight |
| Starts in minutes | Starts in seconds |
| More Memory Usage | Less Memory Usage |
| Larger Size | Smaller Size |

---

## 🌐 Docker Hub

Docker Hub is a cloud-based registry used to store, share, and download Docker Images.

---

## 🎯 Interview Questions Practiced

1. What problem does Docker solve?
2. What is a Docker Image?
3. What is a Docker Container?
4. Difference between Image and Container.
5. Difference between Docker and Virtual Machine.
6. Explain Docker Architecture.
7. What happens internally when running `docker run nginx`?
8. What is Docker Hub?

---

## 📝 MCQ Practice

- Docker Fundamentals Quiz - Round 1
- Docker Fundamentals Quiz - Round 2

**Final Score:** **19/20 (95%)** ✅

---

## 📚 Summary

Today I learned the core fundamentals of Docker, including Docker Images, Containers, Docker Hub, Docker Architecture, and the differences between Docker and Virtual Machines. I also completed interview questions and scored **19/20** in the Docker Fundamentals MCQ assessment.
