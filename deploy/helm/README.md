# Movie Analyzer Helm Chart

A Helm chart for deploying the Movie Analyzer application with sentiment analysis capabilities.

## Overview

This Helm chart deploys a complete movie review analysis system with exact configurations from the current manifests.

## Prerequisites

- Kubernetes cluster (1.19+)
- Helm 3.0+
- kubectl configured to access your cluster

## Installation

```bash
# Install with default values
helm install movie-analyzer ./deploy/helm

# Install in a specific namespace
helm install movie-analyzer ./deploy/helm --namespace movie-analyzer --create-namespace

# Upgrade
helm upgrade movie-analyzer ./deploy/helm

# Uninstall
helm uninstall movie-analyzer
```

## Configuration

All values match the exact configurations from the current manifests:
- Backend: 1 replica, 512Mi/500m requests, 1Gi/1000m limits
- Frontend: 1 replica, NodePort 30000
- Model: 1 replica, 256Mi/250m requests, 512Mi/500m limits  
- PostgreSQL: 1 replica, persistent storage enabled

## Accessing the Application

Frontend available at: http://localhost:30000

## Values

See `values.yaml` for all configurable parameters with exact manifest values. 