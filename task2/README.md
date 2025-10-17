# Task 2 — WordPress + MySQL Deployment on Kubernetes

## 🎯 Objective
Deploy a **WordPress** website with a **MySQL** database on Kubernetes using:
- **Secrets** for database credentials  
- **PersistentVolumeClaim (PVC)** for MySQL data storage  
- **Services** for internal and external access  

---
![t21](https://github.com/ImranNadaf/k8s/blob/d7835b670accdacf0e6e9a09241640288cacd318/screenshots/task2/1.jpg)


![t22](https://github.com/ImranNadaf/k8s/blob/d7835b670accdacf0e6e9a09241640288cacd318/screenshots/task2/1.jpg)

---

##  Steps Executed

### 1️⃣ Create a Secret for Database Credentials
```bash
kubectl apply -f mysql-secret.yaml
kubectl apply -f mysql-pvc.yaml --> Created PVC for MySQL
kubectl apply -f mysql-deployment.yaml--> Deployed MySQL
kubectl apply -f mysql-service.yaml--> Deployed MySQL
kubectl apply -f wordpress-deployment.yaml--> Deployed WordPress
kubectl apply -f wordpress-service.yaml--> Deployed WordPress
kubectl get pods
minikube service wordpress-svc --> To access and open it in browser

