# Ильяс Мардалиев

### Backend / Full Stack Developer · DevOps / DevSecOps

**Саратов · Remote / Hybrid · Open to opportunities**

[![GitHub](https://img.shields.io/badge/GitHub-s1kata-181717?style=flat&logo=github)](https://github.com/s1kata)
[![Telegram](https://img.shields.io/badge/Telegram-@kdascvngd-26A5E4?style=flat&logo=telegram)](https://t.me/ilyasmardaliev)
[![Email](https://img.shields.io/badge/Email-mardaliyevilyas12%40gmail.com-EA4335?style=flat&logo=gmail)](mailto:mardaliyevilyas12@gmail.com)

---

## About

Backend / Full Stack Developer with **2 years of production experience** building and operating web and mobile products.

My main production project is **TravelHub** — a travel search and booking platform covering backend, web, mobile, integrations, databases and infrastructure.

I work across the complete product lifecycle:

`Architecture → Backend → API → Database → Integrations → Docker → Kubernetes → CI/CD → Observability`

My current technical direction is **DevOps with a DevSecOps layer**, focusing on reliable deployments, infrastructure automation, observability and security.

---

## Technical Stack

| Area | Technologies |
|---|---|
| **Backend** | PHP, Go, REST API, MySQL, PostgreSQL, JWT, JSON |
| **Frontend / Mobile** | React Native, Expo, TypeScript, JavaScript |
| **Infrastructure** | Linux, Docker, Kubernetes, Kubespray, Helm, Nginx, containerd |
| **CI/CD** | Git, GitHub Actions, Docker Registry, Helm deployments |
| **Observability** | Prometheus, Grafana, Loki, Metrics, Logs, Alerting |
| **Security** | RBAC, Secrets, SecurityContext, NetworkPolicy, Container Security |
| **Integrations** | T-Bank, Tourvisor, CRM SOTA, REST APIs |
| **Tools** | Git, Linux, Postman, Cursor |

---

# Featured Projects

## TravelHub

### Production travel search & booking platform

**PHP · MySQL · REST API · Nginx · Docker · Kubernetes**

[Repository →](https://github.com/s1kata/travelhub-v2)

TravelHub is a production travel platform for searching and booking tours.

I worked across the complete product lifecycle — from application development and integrations to deployment and infrastructure.

### Main components

```text
Web / Mobile Client
        │
        ▼
      Nginx
        │
        ▼
   TravelHub API
     │   │   │
     │   │   └──────────► CRM SOTA
     │   │
     │   └──────────────► T-Bank
     │
     ├──────────────────► Tourvisor
     │
     ▼
   MySQL / Cache
```

### Responsibilities & engineering work

- Backend development
- REST API development
- JWT authentication
- Database design and integration
- Tourvisor API integration
- T-Bank payment integration
- CRM SOTA integration
- Search and dictionary caching
- Background cache warming
- Nginx configuration
- Environment-based configuration
- Production deployment
- Application security
- Deployment documentation

---

# TravelHub Mobile App

### Production mobile application

**React Native · Expo · TypeScript · REST API · JWT**

TravelHub mobile client published through the App Store.

### Features

- Authentication
- Tour search
- Booking workflows
- REST API integration
- CRM integration
- Payment integration
- User account functionality

**App:** TravelHub  
**Platform:** iOS / App Store

---

# TravelHub Search Cache

### Go microservice / sidecar

**Go · Docker · Nginx · systemd · REST API · Caching**

[Repository →](https://github.com/s1kata/microservice)

A Go service introduced alongside the existing PHP application to reduce unnecessary work on the PHP request path.

The service reads cached Tourvisor search data and preserves compatibility with the existing PHP API contract.

### Architecture

```text
                         ┌─────────────────┐
                         │     Client      │
                         └────────┬────────┘
                                  │
                                  ▼
                         ┌─────────────────┐
                         │      Nginx      │
                         └────────┬────────┘
                                  │
                                  ▼
                    ┌─────────────────────────┐
                    │   Go Search Cache       │
                    └──────────┬──────────────┘
                               │
                     ┌─────────┴─────────┐
                     │                   │
                 CACHE HIT          CACHE MISS
                     │                   │
                     ▼                   ▼
               Cached JSON        PHP Application
                                         │
                                         ▼
                                  Tourvisor API
```

### Key engineering points

- Cache-first request processing
- PHP fallback for cache misses
- Compatible JSON response contract
- Docker deployment
- systemd service
- Nginx reverse-proxy integration
- Health endpoint
- Rollback procedure
- Deployment checklist

The cached request path was optimized to approximately **50 ms instead of the previous multi-second PHP bootstrap path**.

---

# Go REST API

### Backend project

**Go · PostgreSQL · Docker · REST**

[Repository →](https://github.com/s1kata/RestApi)

Standalone REST API demonstrating structured backend architecture.

### Architecture

```text
HTTP Client
     │
     ▼
┌─────────────┐
│   Handler   │
└──────┬──────┘
       │
       ▼
┌─────────────┐
│   Storage   │
└──────┬──────┘
       │
       ▼
┌─────────────┐
│ PostgreSQL  │
└─────────────┘
```

### Includes

- HTTP handlers
- Storage layer
- PostgreSQL integration
- CRUD operations
- Filtering
- JSON request / response handling
- Error handling
- Docker environment

---

# REST API Proxy

### Go HTTP proxy

**Go · HTTP · JSON · REST**

[Repository →](https://github.com/s1kata/restapi-proxy)

HTTP proxy service for REST API communication.

### Includes

- HTTP request forwarding
- Routing
- JSON processing
- Error handling
- REST communication
- Separation of API access from clients

---

# DevOps / Infrastructure

My infrastructure work focuses on making applications reproducible, deployable and observable.

## Kubernetes

Current Kubernetes environment:

```text
                    Kubernetes Cluster
                           │
             ┌─────────────┴─────────────┐
             │                           │
       Control Plane                  Worker
             │                           │
             └─────────────┬─────────────┘
                           │
                    Kubernetes API
                           │
          ┌────────────────┼────────────────┐
          │                │                │
     Deployment        Deployment       Deployment
          │                │                │
      ReplicaSet       ReplicaSet       ReplicaSet
          │                │                │
         Pods             Pods             Pods
          │                │                │
          └────────────────┼────────────────┘
                           │
                        Services
```

### Kubernetes work

- Kubernetes cluster deployment
- Kubespray
- Deployments
- ReplicaSets
- Pods
- Services
- ClusterIP
- NodePort
- Labels & selectors
- Endpoint discovery
- Environment variables
- Container images
- containerd
- Nginx
- Application / database communication

---

# Helm

Helm is used to package Kubernetes workloads and manage application releases.

```text
Application
     │
     ▼
 Helm Chart
     │
     ├── values.yaml
     ├── deployment.yaml
     ├── service.yaml
     └── templates/
             │
             ▼
       Kubernetes Cluster
```

### Helm workflow

```text
Chart
  ↓
values.yaml
  ↓
helm install / upgrade
  ↓
Kubernetes resources
  ↓
Pods
  ↓
Services
  ↓
Application
```

---

# CI/CD

The target delivery pipeline is built around automated validation and deployment.

```text
Developer
    │
    ▼
   Git
    │
    ▼
 Lint / Validation
    │
    ▼
   Tests
    │
    ▼
 Application Build
    │
    ▼
 Docker Image
    │
    ▼
Container Registry
    │
    ▼
 Helm Deployment
    │
    ▼
 Kubernetes
    │
    ▼
 Health Check
    │
    ▼
 Production / Test Stand
```

### CI/CD goals

- Automated validation
- Tests
- Application build
- Docker image build
- Image publishing
- Helm-based deployment
- Kubernetes rollout
- Health checks
- Deployment verification
- Rollback capability

---

# Observability

The observability layer is built around metrics, logs and alerting.

```text
                 Application
                      │
                      ▼
                 Kubernetes
                  │       │
                  │       │
                  ▼       ▼
             Prometheus   Loki
                  │       │
                  └───┬───┘
                      │
                      ▼
                   Grafana
                      │
                      ▼
                   Alerts
```

### Focus areas

- Application metrics
- Infrastructure metrics
- Kubernetes metrics
- Centralized logging
- Dashboards
- Alerting
- Incident investigation
- Performance troubleshooting

---

# DevSecOps

Security is treated as part of the delivery process rather than a separate stage.

### Kubernetes security

- RBAC
- ServiceAccounts
- Secrets
- SecurityContext
- NetworkPolicy
- Least-privilege access

### Container security

- Image scanning
- Dependency checks
- Secret detection
- Secure registry workflow

### CI/CD security

```text
Code
  ↓
Validation
  ↓
Tests
  ↓
Security Checks
  ↓
Docker Image
  ↓
Image Scan
  ↓
Registry
  ↓
Controlled Deployment
```

---

# Troubleshooting Approach

When a system fails, I prefer to identify the root cause instead of applying random fixes.

```text
Symptom
   │
   ▼
Metrics
   │
   ▼
Logs
   │
   ▼
Hypothesis
   │
   ▼
Verification
   │
   ▼
Root Cause
   │
   ▼
Fix
   │
   ▼
Validation
```

Typical Kubernetes troubleshooting flow:

```text
Pod status
    ↓
kubectl describe
    ↓
Events
    ↓
Logs
    ↓
Deployment
    ↓
Service
    ↓
Selector / Labels
    ↓
Endpoints
    ↓
Network / Ports
    ↓
Root Cause
```

---

# Engineering Approach

I work with the system as a whole rather than focusing only on application code.

```text
Client
  ↓
API
  ↓
Application
  ↓
Database
  ↓
External Services
  ↓
Container
  ↓
Kubernetes
  ↓
CI/CD
  ↓
Observability
  ↓
Security
```

My approach:

- Understand the system before changing it
- Prefer simple and reproducible solutions
- Verify assumptions through logs, metrics and system state
- Keep deployment and rollback procedures documented
- Consider application and infrastructure together
- Use AI-assisted development as an accelerator while keeping architecture, decisions and verification under my control

---

# Current Technical Direction

### Backend + Full Stack + DevOps + DevSecOps

```text
                    Engineering
                         │
          ┌──────────────┼──────────────┐
          │              │              │
       Backend       Full Stack       DevOps
          │              │              │
          │              │       ┌──────┼──────┐
          │              │       │      │      │
          │              │    Docker  K8s   CI/CD
          │              │              │
          │              │       ┌──────┼──────┐
          │              │       │      │      │
          │              │     Helm  Ansible  IaC
          │              │
          └──────────────┼─────────────────────┐
                         │                     │
                    DevSecOps             Observability
                         │                     │
                  ┌──────┼──────┐        ┌────┼────┐
                  │      │      │        │    │    │
                 RBAC  Images  CI/CD   Prom  Grafana Loki
```

---

# What I Build

I am interested in systems where development and infrastructure meet:

- Backend services
- REST APIs
- Full Stack applications
- Microservices
- Dockerized applications
- Kubernetes environments
- CI/CD pipelines
- Observability
- Infrastructure automation
- DevSecOps
- Production troubleshooting

---

# Contact

**GitHub:** https://github.com/s1kata  
**Telegram:** https://t.me/ilyasmardaliev  
**Email:** mardaliyevilyas12@gmail.com  
**Production:** https://travelhub63.ru  
**App Store:** TravelHub
