# Task 3 — Admin Pod with Full Cluster Access

## 🎯 Objective
Deploy a Pod in the **admin namespace** that has **full access** to all Kubernetes cluster resources  
using a **ServiceAccount** bound to the **cluster-admin** role.

---


![t31](https://github.com/ImranNadaf/k8s/blob/d7835b670accdacf0e6e9a09241640288cacd318/screenshots/task3/1.jpg)

![t31](https://github.com/ImranNadaf/k8s/blob/d7835b670accdacf0e6e9a09241640288cacd318/screenshots/task3/2.jpg)

![t31](https://github.com/ImranNadaf/k8s/blob/d7835b670accdacf0e6e9a09241640288cacd318/screenshots/task3/3.jpg)


##  Steps Executed

```bash
kubectl apply -f admin-namespace.yaml
kubectl apply -f admin-serviceaccount.yaml
kubectl get ns
kubectl -n admin get sa
kubectl apply -f clusterrolebinding.yaml
kubectl apply -f admin-pod.yaml
kubectl -n admin get pods
kubectl -n admin exec -it admin-pod -- /bin/sh  jumped in admin-pod
kubectl get pods -A
kubectl get nodes
