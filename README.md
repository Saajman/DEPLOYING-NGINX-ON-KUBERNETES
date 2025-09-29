# Deploying Nginx on Kubernetes

## 📋 Project Overview
This project demonstrates the deployment of Nginx web server on a Kubernetes cluster using Minikube. The deployment includes customization of the default Nginx page, service exposure, scaling, and rolling updates.

## 🎯 Objectives
- [x] Deploy Nginx on Kubernetes
- [x] Manage deployments and scaling
- [x] Expose the application externally via Service
- [x] Document the entire process

## 🛠️ Tools Used
- **Kubernetes Environment**: Minikube
- **CLI Tool**: kubectl
- **Application**: Nginx Web Server
- **System Requirements**: 
  - Installed Docker
  - Working Kubernetes CLI

## 📁 Project Structure
```
project/
├── deployment.yml    # Kubernetes deployment manifest
├── service.yml       # Kubernetes service manifest
├── index.html        # Custom HTML page
└── README.md         # Project documentation
```

## 🚀 Implementation Steps

### Task 1: Selecting Sample Application
**Chosen App**: Nginx
- **Why Nginx?**: Lightweight, easy to deploy, and supports customization

### Task 2: Environment Setup
```bash
minikube start
kubectl version
```

### Task 3: Creating Deployment Manifest
- Created `deployment.yml` defining container image, replicas, and ports
- Created custom HTML file with message: **"Hello from Saajman's Kubernetes"**

### Task 4: Exposing the Application
- Created `service.yml` using NodePort to make the app accessible externally
- Applied configurations:
```bash
kubectl apply -f deployment.yml
kubectl apply -f service.yml
kubectl get pods
```

### Task 5: Deployment and Testing
```bash
minikube service nginx-service
```
- Verified the custom landing page was accessible via browser

### Task 6: Scaling and Updates
**Scaling**:
```bash
kubectl scale deployment/nginx-deployment --replicas=5
kubectl get pods
```

**Benefits of Scaling**:
- Improved availability
- Load balancing across replicas
- Faster response times
- Increased capacity

**Rolling Updates**:
```bash
kubectl set image deployment/nginx-deployment nginx=nginx:latest
kubectl rollout status deployment/nginx-deployment
```

## 🐛 Issues and Troubleshooting
- **Issue**: Pod not creating properly
- **Fix**: Restarted Minikube and re-applied all YAML configurations

## ✅ Key Achievements
- [x] Successfully deployed and exposed Nginx application
- [x] Implemented scaling from 1 to 5 replicas
- [x] Performed rolling updates without downtime
- [x] Practiced writing and applying YAML configurations
- [x] Gained hands-on experience with Kubernetes concepts

## 📝 Conclusion
This project provided practical experience in deploying containerized applications on Kubernetes, managing deployments, scaling applications, and performing updates while maintaining service availability. The team successfully demonstrated end-to-end Kubernetes deployment workflows using Nginx as the sample application.

---
**Kubernetes Nginx Deployment Project**
