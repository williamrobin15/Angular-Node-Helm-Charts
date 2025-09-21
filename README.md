 # **Angular & Node Helm Charts**

Helm charts for deploying a full-stack application with **Angular frontend** and **Node.js backend** on Kubernetes. Simplifies multi-environment deployments and scaling.

## Project Structure

```

.
├── helm-frontend-angular/   # Angular frontend Helm chart
├── helm-backend-node/       # Node.js backend Helm chart
└── README.md

````

## Prerequisites

- Kubernetes cluster & `kubectl` configured  
- Helm v3+ installed  
- Docker images for Angular & Node.js pushed to a registry

## Deployment

### Frontend (Angular)

```bash
helm upgrade --install angular-frontend ./helm-frontend-angular \
  --namespace <namespace> \
  --values ./helm-frontend-angular/values.yaml
````

### Backend (Node.js)

```bash
helm upgrade --install node-backend ./helm-backend-node \
  --namespace <namespace> \
  --values ./helm-backend-node/values.yaml
```

### Deploy Both

```bash
helm upgrade --install angular-frontend ./helm-frontend-angular --namespace fullstack
helm upgrade --install node-backend ./helm-backend-node --namespace fullstack
```

## Configuration

Edit `values.yaml` in each chart to set:

* **Docker image & tag**
* **Ports & replicas**
* **Ingress / Service settings**

