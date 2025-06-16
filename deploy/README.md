# Movie Analyzer Kubernetes Deployment

This directory contains organized Kubernetes manifests for deploying the Movie Analyzer application.

## Directory Structure

```
deploy/
├── manifests/
│   ├── namespace.yaml              # Namespace definition
│   ├── backend/
│   │   ├── deployment.yaml         # Backend Spring Boot application
│   │   ├── service.yaml           # Backend service (ClusterIP)
│   │   └── secret.yaml            # Backend database credentials (movieuser)
│   ├── frontend/
│   │   ├── deployment.yaml         # Frontend React/Express application
│   │   ├── service.yaml           # Frontend service (NodePort)
│   │   └── ingress.yaml           # Ingress for production use (optional)
│   ├── model/
│   │   ├── deployment.yaml         # Model server (Python Flask)
│   │   └── service.yaml           # Model service (ClusterIP)
│   └── postgres/
│       ├── deployment.yaml         # PostgreSQL database
│       ├── service.yaml           # Database service (ClusterIP)
│       ├── pvc.yaml               # Persistent volumes
│       ├── secret.yaml            # Database initialization credentials (postgres)
│       └── configmap.yaml         # Database initialization scripts
├── deploy.sh                      # Deployment automation script
└── README.md                      # This file
```

## Quick Start

### Deploy the Application

```bash
# Deploy everything
./deploy/deploy.sh deploy
```

### Check Status

```bash
./deploy/deploy.sh status
```

### Access the Application

Frontend available at: http://localhost:30000

### Clean Up

```bash
./deploy/deploy.sh cleanup
``` 