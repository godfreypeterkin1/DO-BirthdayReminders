# Birthday Bot Deployment on DigitalOcean Kubernetes (DOKS)

This repository contains Kubernetes manifests to deploy the `birthday-bot` web application using DigitalOcean Kubernetes, including load balancing and autoscaling.

## 📦 What's Included
- `deployment.yaml`: Deploys 2 pods of the birthday bot using a public Docker image
- `service.yaml`: Exposes the app using a DigitalOcean LoadBalancer on port 80
- `hpa.yaml`: Enables Horizontal Pod Autoscaler (HPA) based on CPU usage

## 🚀 How to Use

1. Apply the deployment:
   ```
   kubectl apply -f deployment.yaml
   ```

2. Apply the service:
   ```
   kubectl apply -f service.yaml
   ```

3. Apply the autoscaler:
   ```
   kubectl apply -f hpa.yaml
   ```

4. Get the external IP of the service:
   ```
   kubectl get svc birthday-bot-service
   ```

5. Visit the IP in your browser to access the app.

## 📌 Notes
- App image: `ghcr.io/do-community/birthday-bot:main`
- Port: `8080` (internally), `80` (publicly)
- Resource requests and limits are configured for autoscaling

---
