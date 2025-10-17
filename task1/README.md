# Task 1 — Multi-Pod NGINX Deployment on Kubernetes

## 🎯 Objective
Deploy three different NGINX Pods in Kubernetes, each serving a unique HTML page,  
and expose them through a single Service to demonstrate load balancing.

---

##   Steps Executed
Started Cluster-->minikube start –driver=docker

### 1️⃣ Build Custom Docker Images
Each Pod serves a unique HTML file.

![t1](screenshots/task1/1.jpg)

![t2](screenshots/task1/2.jpg)

![t3](screenshots/task1/3.jpg)

![t4](screenshots/task1/4.jpg)

```bash
# Build
docker build -t imrannadaf/nginx-pod1:v1 -f Dockerfile1 .
docker build -t imrannadaf/nginx-pod2:v1 -f Dockerfile2 .
docker build -t imrannadaf/nginx-pod3:v1 -f Dockerfile3 .

# Pushed to Docker Hub
docker push imrannadaf/nginx-pod1:v1
docker push imrannadaf/nginx-pod2:v1
docker push imrannadaf/nginx-pod3:v1

Then
kubectl apply -f task1/deployment.yaml
kubectl apply -f task1/service.yaml
kubectl get pods -o wide
kubectl get svc
minikube service multi-nginx-svc

