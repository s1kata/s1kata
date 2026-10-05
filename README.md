Ильяс Мардалиев

Backend / Full Stack Developer · DevOps / DevSecOps
Саратов · Remote / Hybrid · Open to opportunities

⸻

About

Backend / Full Stack Developer with 2 years of production experience building and operating web and mobile products.

I work across the full product lifecycle — from application architecture and backend/API development to databases, third-party integrations, containerization, deployment and infrastructure.

My main production project is TravelHub, a travel search and booking platform that I developed and maintained across web, mobile and backend components.

I also work with Go, Docker and Kubernetes, with a focus on reproducible deployments, service architecture and reliable application delivery.

My current engineering focus is DevOps with a DevSecOps layer: CI/CD, Kubernetes, observability, infrastructure automation, container security and secure delivery practices.

⸻

Core Stack

Backend

PHP Go REST API MySQL PostgreSQL JWT JSON

Frontend / Mobile

React Native Expo TypeScript JavaScript Tailwind CSS

DevOps / Infrastructure

Linux Docker containerd Kubernetes Kubespray Helm Nginx systemd Git CI/CD

Observability

Prometheus Grafana Loki Metrics Logs Alerting Troubleshooting

Security

RBAC Secrets SecurityContext NetworkPolicy Container Security DevSecOps

Integrations

T-Bank Tourvisor CRM SOTA External REST APIs

Tools

Git Linux Postman Cursor AI-assisted development

⸻

Featured Projects

TravelHub — Production Platform

PHP · MySQL · REST API · Nginx · Docker · Kubernetes

github.com/s1kata/travelhub-v2

Production travel search and booking platform.

The project covers the complete application lifecycle — backend, REST API, database, external integrations, caching, deployment and infrastructure.

Key areas

* Travel search and booking
* REST API for the mobile application
* JWT authentication
* Tourvisor integration
* T-Bank payment integration
* CRM integration
* Search and dictionary caching
* Background cache warming
* Nginx reverse proxy
* Environment-based configuration
* Deployment documentation
* Application security

High-level architecture

flowchart LR
    Client["Web / Mobile Client"]
    Nginx["Nginx"]
    API["TravelHub API"]
    DB[("MySQL")]
    Tourvisor["Tourvisor API"]
    Bank["T-Bank"]
    CRM["CRM SOTA"]
    Cache["Search Cache"]
    Client --> Nginx
    Nginx --> API
    API --> DB
    API --> Cache
    API --> Tourvisor
    API --> Bank
    API --> CRM

⸻

TravelHub Mobile App

React Native · Expo · TypeScript · JWT · REST API

Production mobile client for the TravelHub platform.

* Authentication
* Tour search
* Booking workflows
* REST API integration
* CRM integration
* Payment integration
* Production App Store release

⸻

TravelHub Search Cache — Go Microservice

Go · Docker · Nginx · systemd · REST API · Caching

github.com/s1kata/microservice

A Go sidecar introduced alongside the existing PHP application to reduce unnecessary work on the PHP request path.

The service reads cached Tourvisor search data and preserves compatibility with the existing PHP API contract.

Architecture

flowchart LR
    Client["Client"]
    Nginx["Nginx"]
    Go["Go Search Cache"]
    Cache[("Search Cache")]
    PHP["PHP Application"]
    Tourvisor["Tourvisor API"]
    Client --> Nginx
    Nginx --> Go
    Go --> Cache
    Go -->|Cache HIT| Client
    Go -->|Cache MISS| PHP
    PHP --> Tourvisor
    PHP --> Cache

Deployment architecture

flowchart TB
    Host["Linux Host"]
    Docker["Docker"]
    Go["Go Sidecar"]
    PHP["PHP Application"]
    Nginx["Nginx"]
    Systemd["systemd"]
    Host --> Docker
    Docker --> Go
    Host --> PHP
    Host --> Nginx
    Systemd --> Go
    Nginx --> Go
    Nginx --> PHP

Key points

* Go HTTP service for cached search data
* Cache-first request processing
* PHP fallback for cache misses
* Compatible JSON contract
* Docker deployment
* systemd service
* Nginx reverse-proxy integration
* Health endpoint
* Rollback procedure
* Production deployment checklist

The cached request path was optimized to approximately 50 ms instead of the previous multi-second PHP bootstrap path.

⸻

Go REST API

Go · PostgreSQL · Docker · REST

github.com/s1kata/RestApi

A standalone backend project demonstrating structured REST API architecture.

Architecture

flowchart TB
    Client["HTTP Client"]
    Handler["HTTP Handlers"]
    Storage["Storage Layer"]
    DB[("PostgreSQL")]
    Client --> Handler
    Handler --> Storage
    Storage --> DB

Includes

* HTTP handlers
* Storage layer
* PostgreSQL integration
* CRUD operations
* Filtering
* JSON request/response handling
* Error handling
* Docker environment
* Separate proxy component

⸻

REST API Proxy

Go · HTTP · JSON · REST

github.com/s1kata/restapi-proxy

HTTP proxy service for the Go REST API.

* Request routing
* HTTP communication
* JSON processing
* Error handling
* Request forwarding
* Separation of API access from clients

⸻

DevOps / Infrastructure

My infrastructure work focuses on running the application reliably rather than treating deployment as a separate step.

Application delivery

flowchart LR
    Code["Source Code"]
    Git["Git"]
    CI["CI/CD"]
    Image["Container Image"]
    Registry["Container Registry"]
    Helm["Helm"]
    K8s["Kubernetes"]
    Service["Kubernetes Service"]
    Nginx["Nginx / Ingress"]
    Code --> Git
    Git --> CI
    CI --> Image
    Image --> Registry
    Registry --> Helm
    Helm --> K8s
    K8s --> Service
    Service --> Nginx

Kubernetes architecture

flowchart TB
    User["External User"]
    Ingress["Ingress / Nginx"]
    ServiceWeb["Web Service"]
    ServiceApp["App Service"]
    ServiceDB["DB Service"]
    Web["Web Pod"]
    App["App Pod"]
    DB["MySQL Pod"]
    User --> Ingress
    Ingress --> ServiceWeb
    ServiceWeb --> Web
    Web --> ServiceApp
    ServiceApp --> App
    App --> ServiceDB
    ServiceDB --> DB

Kubernetes concepts

* Control plane / worker architecture
* Deployments
* ReplicaSets
* Pods
* Services
* ClusterIP
* NodePort
* Labels and selectors
* Endpoint discovery
* Environment configuration
* Container images
* containerd
* Kubespray
* Helm

⸻

CI/CD

Current delivery architecture:

flowchart LR
    Developer["Developer"]
    Git["Git"]
    Lint["Lint"]
    Test["Tests"]
    Build["Build"]
    Docker["Docker Image"]
    Registry["Container Registry"]
    Deploy["Helm Deploy"]
    K8s["Kubernetes"]
    Health["Health Check"]
    Developer --> Git
    Git --> Lint
    Lint --> Test
    Test --> Build
    Build --> Docker
    Docker --> Registry
    Registry --> Deploy
    Deploy --> K8s
    K8s --> Health

The target pipeline is designed around:

* Source validation
* Automated tests
* Application build
* Docker image build
* Image publishing
* Kubernetes deployment
* Helm-based releases
* Deployment verification
* Health checks
* Rollback capability

⸻

Observability

The observability stack is built around metrics, logs and alerting.

flowchart LR
    App["Application"]
    K8s["Kubernetes"]
    Prom["Prometheus"]
    Grafana["Grafana"]
    Loki["Loki"]
    Alert["Alerting"]
    App --> K8s
    K8s --> Prom
    K8s --> Loki
    Prom --> Grafana
    Loki --> Grafana
    Prom --> Alert

The goal is to be able to move from:

Symptom → Metrics → Logs → Hypothesis → Verification → Root Cause → Fix

rather than troubleshooting by trial and error.

⸻

Security / DevSecOps

The infrastructure direction includes security controls at both application and Kubernetes levels.

Kubernetes security

* RBAC
* ServiceAccounts
* Secrets
* SecurityContext
* NetworkPolicy
* Least-privilege access
* Container security

CI/CD security

* Image scanning
* Dependency checks
* Secret detection
* Secure registry workflow
* Controlled deployment permissions

⸻

Engineering Approach

I focus on the complete system rather than isolated components.

flowchart LR
    Client["Client"]
    API["API"]
    App["Application"]
    DB[("Database")]
    External["External Services"]
    Container["Containers"]
    K8s["Infrastructure"]
    Obs["Observability"]
    Client --> API
    API --> App
    App --> DB
    App --> External
    App --> Container
    Container --> K8s
    K8s --> Obs

When something breaks, I approach the problem systematically:

flowchart LR
    Symptom["Symptom"]
    Metrics["Metrics"]
    Logs["Logs"]
    Hypothesis["Hypothesis"]
    Verify["Verification"]
    Root["Root Cause"]
    Fix["Fix"]
    Validate["Validation"]
    Symptom --> Metrics
    Metrics --> Logs
    Logs --> Hypothesis
    Hypothesis --> Verify
    Verify --> Root
    Root --> Fix
    Fix --> Validate

I use AI-assisted development as an engineering accelerator while keeping architecture, technical decisions, verification and system behavior under my control.

⸻

Current Technical Direction

Backend + Full Stack + DevOps + DevSecOps

flowchart TB
    Backend["Backend"]
    FullStack["Full Stack"]
    DevOps["DevOps"]
    DevSecOps["DevSecOps"]
    Backend --> DevOps
    FullStack --> DevOps
    DevOps --> DevSecOps
    DevOps --> Kubernetes["Kubernetes"]
    DevOps --> Helm["Helm"]
    DevOps --> CICD["CI/CD"]
    DevOps --> Ansible["Ansible"]
    DevOps --> Observability["Observability"]
    DevOps --> IaC["Infrastructure as Code"]
    DevOps --> GitOps["GitOps"]
    DevSecOps --> K8sSecurity["Kubernetes Security"]
    DevSecOps --> ImageSecurity["Container / Image Security"]
    DevSecOps --> PipelineSecurity["CI/CD Security"]

⸻

Contact

* GitHub: https://github.com/s1kata
* Telegram: https://t.me/ilyasmardaliev
* Email: mardaliyevilyas12@gmail.com
* Production: https://travelhub63.ru
* App Store: TravelHub
