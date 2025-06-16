# Movie Analyzer Kubernetes Manifests

This directory contains organized Kubernetes manifests for deploying the Movie Analyzer application.

## Directory Structure

```
manifests/
├── namespace.yaml              # Namespace definition
├── backend/
│   ├── deployment.yaml         # Backend Spring Boot application
│   ├── service.yaml           # Backend service (ClusterIP)
│   └── secret.yaml            # Backend database credentials (movieuser)
├── frontend/
│   ├── deployment.yaml         # Frontend React/Express application
│   ├── service.yaml           # Frontend service (NodePort)
│   └── ingress.yaml           # Ingress for production use (optional)
├── model/
│   ├── deployment.yaml         # Model server (Python Flask)
│   └── service.yaml           # Model service (ClusterIP)
├── postgres/
│   ├── deployment.yaml         # PostgreSQL database
│   ├── service.yaml           # Database service (ClusterIP)
│   ├── pvc.yaml               # Persistent volumes
│   ├── secret.yaml            # Database initialization credentials (postgres)
│   └── configmap.yaml         # Database initialization scripts
├── deploy.sh                  # Deployment automation script
├── kustomization.yaml         # Kustomize configuration (alternative deployment)
└── README.md                  # This file
```

## Quick Start

### Deploy the Application

```bash
# Deploy everything
./deploy.sh deploy
```

### Check Status

```bash
./deploy.sh status
```

### Access the Application

Frontend available at: http://localhost:30000

### Clean Up

```bash
./deploy.sh cleanup
```

## Alternative Deployment with Kustomize

You can also deploy using Kustomize:

```bash
# Deploy with kustomize
kubectl apply -k .

# Delete with kustomize
kubectl delete -k .
``` 