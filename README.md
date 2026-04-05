# 🚀 Kubernetes Multi-Tier App (Node.js + Spring Boot + PostgreSQL)

A simple DevOps project to **containerize and deploy a 3-tier application** using Docker and Kubernetes (Minikube).

![image alt](https://github.com/sarat2729/devops-assignment1/blob/24e3f21503270467b09bac85574806819907b7b4/Kubernetes%20architecture%20with%20Minikube%20deployment.png)
---

## 📌 What This Project Does

* Frontend (Node.js) → UI
* Backend (Spring Boot) → API & logic
* Database (PostgreSQL) → Data storage
* Kubernetes → Runs everything together

---

## 🏗️ Architecture

```
Browser → Frontend (:3000) → Backend (:8080) → PostgreSQL (:5432)
```

---

## ⚙️ Tech Stack

* Frontend: Node.js (Express, EJS)
* Backend: Java 17 + Spring Boot
* Database: PostgreSQL
* Container: Docker
* Orchestration: Kubernetes (Minikube)

---

## 🔧 Prerequisites

Install:

* Docker → **https://www.docker.com/products/docker-desktop/**
* Minikube → **https://minikube.sigs.k8s.io/docs/start/**
* kubectl → **https://kubernetes.io/docs/tasks/tools/**
* Java 17 → **https://adoptium.net/**
* Maven → **https://maven.apache.org/**

---

## 🚀 Quick Start

### 1. Start Cluster

```bash
minikube start --driver=docker --memory=4096
```

---

### 2. Build Images

```bash
docker build -t banking-backend:v1 ./backend
docker build -t banking-frontend:v1 ./frontend
```

---

### 3. Load into Minikube

```bash
minikube image load banking-backend:v1
minikube image load banking-frontend:v1
```

---

### 4. Deploy

```bash
kubectl apply -f k8s/
```

---

### 5. Access App

```bash
minikube service frontend -n banking-app
```

---

## ✅ Verify

```bash
kubectl get pods -n banking-app
```

Expected:

* 1 postgres
* 2 backend
* 2 frontend

---

## ⚠️ Common Issues

* Backend slow start → wait ~30s (Spring Boot)
* DB errors → check service name `postgres`
* Frontend error → ensure `http://backend:8080`

---

## 🧹 Cleanup

```bash
kubectl delete namespace banking-app
minikube delete
```

---

## 📌 Key Learnings

* Docker multi-stage builds
* Kubernetes deployments & services
* ConfigMaps, Secrets, PVC
* Debugging real-world apps

---

## ⭐ Next Steps

* Add CI/CD (GitHub Actions / Jenkins)
* Deploy to AWS EKS
* Add monitoring (Prometheus, Grafana)

---



Add monitoring (Prometheus, Grafana)

⭐ Star the repo if this helped!
