# DevSecOps Assessment Test

**Version:** `1.0.0`

| Information | Value |
|------------|-------|
| Project Type | DevSecOps Technical Assessment |
| Target Application | OWASP WebGoat |
| Java Version | Java 25 (WebGoat) |
| Build Tool | Apache Maven |
| Container Platform | Docker |
| Container Orchestration | Kubernetes (Minikube) |
| Security Tools | SonarQube, Snyk, Nikto |

---

# Overview

Repository ini berisi penyelesaian **DevSecOps Assessment Test** yang mencakup implementasi konsep DevSecOps, Git Workflow, Security Scanning, hingga deployment menggunakan Kubernetes.

Assessment dilakukan menggunakan aplikasi **OWASP WebGoat** sebagai target security testing.

Seluruh dokumentasi, konfigurasi, manifest, output command, dan hasil scanning disimpan di dalam repository ini sebagai evidence pengerjaan.

---

# Tech Stack

### Programming Language

- Java

### Build Tool

- Apache Maven

### Version Control

- Git
- GitHub

### Container

- Docker

### Container Orchestration

- Kubernetes
- Minikube

### Security Scanning

- SonarQube (SAST)
- Snyk (SCA)
- Nikto (DAST)

### CLI

- kubectl
- Docker CLI
- Git CLI

---

# Assessment Tasks

| Task | Description | Status |
|------|-------------|--------|
| Task 01 | DevSecOps Fundamentals | ✅ Completed |
| Task 02 | Git Workflow | ✅ Completed |
| Task 03 | Security Scanning | ✅ Completed |
| Task 04 | Kubernetes Deployment | ✅ Completed |
| Task 05 | Documentation | 🚧 In Progress |

---

# Repository Structure

```text
devsecops-assessment-test/
├── Task Challenge - DevSecOps Engineer.pdf
├── README.md
├── task-01-devsecops
├── task-02-git
├── task-03-security-scanning
│   ├── WebGoat
│   ├── sonarqube
│   ├── snyk
│   └── nikto
├── task-04-kubernetes
│   ├── manifests
│   └── outputs
└── task-05-documentation
    ├── report
    ├── presentation
    └── outputs
```

---

# Task Summary

## Task 01 — DevSecOps

Materi yang dibahas:

- DevOps
- DevSecOps
- SDLC
- Monolithic Architecture
- Microservices Architecture
- DevSecOps Lifecycle

---

## Task 02 — Git

Implementasi Git Workflow meliputi:

- Repository Initialization
- Git Branching
- Development Branch
- Master Branch
- Git Merge
- Git Commit
- Git Push

---

## Task 03 — Security Scanning

Implementasi beberapa security tools.

### SonarQube (SAST)

Melakukan static source code analysis terhadap OWASP WebGoat.

Output:

- Dashboard
- Issues
- Security Hotspots
- Activity
- Project Overview

Lokasi:

```
task-03-security-scanning/sonarqube/
```

---

### Snyk (SCA)

Dependency vulnerability scanning.

Output:

- snyk-report.txt
- snyk-report.json

Lokasi:

```
task-03-security-scanning/snyk/
```

---

### Nikto (DAST)

Dynamic Web Security Assessment.

Output:

- nikto-report.txt

Lokasi:

```
task-03-security-scanning/nikto/
```

---

# Task 04 — Kubernetes

Deployment Apache HTTP Server menggunakan Kubernetes pada Minikube.

Dokumen yang tersedia:

- Kubernetes Deployment Manifest
- Kubernetes Service Manifest
- kubectl Output
- Minikube Service URL
- Apache Homepage Output

Lokasi:

```
task-04-kubernetes/
```

---

# Prerequisites

Software yang digunakan selama assessment.

- Git
- Docker
- Java 25
- Apache Maven
- kubectl
- Minikube
- SonarQube
- SonarScanner
- Snyk CLI
- Nikto

---

# Build & Run

## Clone Repository

```bash
git clone https://github.com/<username>/devsecops-assessment-test.git

cd devsecops-assessment-test
```

---

## Task 03

Masuk ke folder:

```bash
cd task-03-security-scanning
```

Ikuti README pada masing-masing tools.

- SonarQube
- Snyk
- Nikto

---

## Task 04

Masuk ke folder manifest.

```bash
cd task-04-kubernetes/manifests
```

Deploy Kubernetes.

```bash
kubectl apply -f apache-deployment.yaml

kubectl apply -f apache-service.yaml
```

Verifikasi.

```bash
kubectl get nodes

kubectl get deployments

kubectl get pods

kubectl get svc
```

---

# Documentation

Seluruh dokumentasi assessment berada pada:

```
task-05-documentation/
```

Berisi:

- Final Report
- Presentation
- Assessment Output

---

# Project Status

| Module | Status |
|---------|--------|
| DevSecOps | ✅ |
| Git | ✅ |
| SonarQube | ✅ |
| Snyk | ✅ |
| Nikto | ✅ |
| Kubernetes | ✅ |
| Documentation | 🚧 |

---

# Changelog

## v1.0.0

Initial DevSecOps Assessment Repository.

Implemented:

- DevSecOps Documentation
- Git Workflow
- SonarQube Integration
- Snyk Dependency Scan
- Nikto DAST Scan
- Kubernetes Deployment using Minikube
- Project Documentation

---

# License

This repository was created for a **DevSecOps Engineer Technical Assessment**.

Copyright © 2026 Dino Darmayanto

All Rights Reserved.