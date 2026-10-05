Backend / Full Stack Developer with 2 years of production experience building and operating web and mobile products.

I work across the full product lifecycle — from application architecture and backend/API development to databases, third-party integrations, containerization, deployment and infrastructure.

My main production project is TravelHub, a travel search and booking platform that I developed and maintained across web, mobile and backend components.

I also work with Go, Kubernetes, Docker, Helm and infrastructure automation, with a focus on building reproducible deployment environments and reliable application delivery.

My current technical focus is DevOps with a DevSecOps layer: CI/CD, Kubernetes, observability, infrastructure automation, container security and secure delivery practices.


Core Stack

Backend

PHP Go REST API MySQL PostgreSQL JWT JSON

Frontend / Mobile

React Native Expo TypeScript JavaScript Tailwind CSS

Infrastructure / DevOps

Linux Docker containerd Kubernetes Kubespray Helm Nginx systemd Git CI/CD

Observability / Operations

Prometheus Grafana Loki Alerting Logs Metrics Troubleshooting

Security

Kubernetes Security RBAC Secrets SecurityContext NetworkPolicy Container Security DevSecOps

Integrations

T-Bank Tourvisor CRM SOTA External REST APIs

Tools

Git Linux Postman Cursor AI-assisted development

Featured Projects

TravelHub — Production Platform

PHP · MySQL · REST API · Nginx · JavaScript · Docker · Kubernetes

github.com/s1kata/travelhub-v2⁠￼

Production travel platform for search and booking tours.

The project covers the complete application lifecycle: backend, REST APIs, database, external integrations, deployment, scheduled jobs, caching and operational infrastructure.

Key areas

* Travel search and booking workflows
* REST API for the mobile application
* JWT-based authentication
* Integration with Tourvisor
* Payment integration with T-Bank
* CRM integration
* Search and dictionary caching
* Background cache warming through scheduled jobs
* Nginx reverse proxy configuration
* Production deployment documentation
* Runtime configuration through environment variables
* Application security and deployment documentation

The repository contains dedicated deployment documentation, cron configuration, API documentation, caching architecture and operational procedures.

TravelHub Mobile App — Production

React Native · Expo · TypeScript · JWT · REST API

Mobile client for the TravelHub platform.

* Authentication and user flows
* REST API integration
* Tour search
* Booking workflows
* CRM integration
* Payment integration
* Production release through the App Store

TravelHub Search Cache — Go Microservice

Go · Docker · Nginx · systemd · REST API · caching

github.com/s1kata/microservice⁠￼

A Go sidecar introduced alongside the existing PHP application to reduce unnecessary work on the PHP request path.

The service reads the existing Tourvisor cache and preserves compatibility with the existing PHP API contract.

Architecture
Client
   │
   ▼
 Nginx
   │
   ├── Go search-cache-reader
   │       │
   │       ├── cache HIT → cached JSON
   │       │
   │       └── cache MISS → PHP fallback
   │
   └── PHP application
   Key points

* Go HTTP service for cached search data
* Compatible JSON contract with the existing PHP API
* Cache-first request processing
* PHP fallback for cache misses / live searches
* Docker deployment
* systemd service configuration
* Nginx reverse-proxy integration
* Health endpoint
* Rollback procedure
* Production deployment checklist

The sidecar reduced the cached PHP request path from roughly 3 seconds of bootstrap overhead to ~50 ms for cache reads, while keeping the existing application and API contract intact.

The repository also documents a roadmap for further evolution: asynchronous search workers, Redis-based caching and Prometheus metrics.

Go REST API

Go · PostgreSQL · Docker · REST

github.com/s1kata/RestApi⁠￼

A standalone REST API project demonstrating a structured backend architecture.

Includes

* HTTP handlers
* Storage layer
* PostgreSQL integration
* CRUD operations
* Filtering
* JSON request/response handling
* Error handling
* Docker-based environment
* Separate proxy component

The project focuses on keeping HTTP handling, business logic and data access separated rather than putting the entire application into a single layer.

REST API Proxy

Go · HTTP · JSON · REST

github.com/s1kata/restapi-proxy⁠￼

HTTP proxy service for the REST API.

* Request routing
* JSON processing
* HTTP communication
* Error handling
* Request forwarding
* Separation of API access from the client

DevOps / Infrastructure

My infrastructure work is centered around running the application rather than treating deployment as a separate afterthought.

Current infrastructure work includes:
Application
    ↓
Docker
    ↓
Container Registry
    ↓
Kubernetes
    ↓
Deployments
    ↓
Services
    ↓
Nginx / Ingress
    ↓
External traffic

The Kubernetes environment includes:

* Control plane and worker nodes
* Deployments
* ReplicaSets
* Pods
* Services
* ClusterIP
* NodePort
* Labels and selectors
* Endpoint discovery
* Environment configuration
* Container image management
* containerd
* Kubespray
* Helm

The infrastructure is being extended with:

* CI/CD
* Ansible
* Prometheus
* Grafana
* Loki
* Alerting
* Ingress
* Kubernetes security
* Infrastructure as Code
* GitOps

Engineering Approach

I focus on the entire path of a system rather than isolated code:
Client
  ↓
API
  ↓
Application
  ↓
Database
  ↓
External integrations
  ↓
Containers
  ↓
Infrastructure
  ↓
Monitoring
  ↓
Operations

When something breaks, the goal is not simply to restart it.

I work from:
Symptom
   ↓
Metrics
   ↓
Logs
   ↓
Hypothesis
   ↓
Verification
   ↓
Root cause
   ↓
Fix
   ↓
Validation

I use AI-assisted development as an engineering accelerator, while keeping architecture, technical decisions, verification and system behavior under my control.

Current Focus

DevOps + Backend + DevSecOps
Kubernetes
    │
    ├── Helm
    ├── CI/CD
    ├── Ansible
    ├── Observability
    ├── Ingress
    ├── Security
    ├── IaC
    └── GitOps

The goal is to build reliable, reproducible and observable application environments rather than simply deploy containers.

Contact

* GitHub: https://github.com/s1kata
* Telegram: https://t.me/ilyasmardaliev
* Email: mardaliyevilyas12@gmail.com
* Production: https://travelhub63.ru
* App Store: TravelHub
