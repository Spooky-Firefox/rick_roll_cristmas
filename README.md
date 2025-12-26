# 🎄 Rick Roll Christmas 🎅

A festive ArgoCD application that redirects unsuspecting users to the classic Rick Roll!

## 📁 Project Structure

```
├── argocd/
│   └── application.yaml    # ArgoCD Application manifest
├── k8s/
│   ├── configmap.yaml      # Nginx redirect configuration
│   ├── deployment.yaml     # Nginx deployment
│   ├── ingress.yaml        # Ingress for external access
│   ├── kustomization.yaml  # Kustomize configuration
│   └── service.yaml        # Kubernetes service
└── README.md
```

## 🚀 Deployment

### Prerequisites

- Kubernetes cluster
- ArgoCD installed
- Ingress controller (optional, for external access)

### Steps

1. **Update the Git repository URL** in `argocd/application.yaml`:
   ```yaml
   repoURL: https://github.com/YOUR_USERNAME/rick_roll_cristmas.git
   ```

2. **Update the Ingress hostname** in `k8s/ingress.yaml`:
   ```yaml
   host: your-domain.com
   ```

3. **Push to your Git repository**:
   ```bash
   git init
   git add .
   git commit -m "🎄 Initial Rick Roll deployment"
   git remote add origin https://github.com/YOUR_USERNAME/rick_roll_cristmas.git
   git push -u origin main
   ```

4. **Deploy the ArgoCD Application**:
   ```bash
   kubectl apply -f argocd/application.yaml
   ```

5. **Watch ArgoCD sync the application**:
   ```bash
   argocd app get rickroll-christmas
   ```

## 🧪 Testing Locally

Without ArgoCD, you can test with:

```bash
kubectl create namespace rickroll
kubectl apply -k k8s/
kubectl port-forward svc/rickroll 8080:80 -n rickroll
```

Then visit http://localhost:8080 and enjoy! 🕺

## 🎁 Merry Christmas!

Never gonna give you up, never gonna let you down! 🎵
