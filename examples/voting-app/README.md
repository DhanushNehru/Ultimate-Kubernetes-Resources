# voting-app
This repository contains Kubernetes configuration files to deploy a complete Voting App setup using the following components:

- PostgreSQL (Database)
- Redis (Caching)
- Voting App (Frontend)
- Worker App (Backend processing)
- Result App (Result display)

### Prerequisites
Make sure you have the following installed:

- Kubernetes (minikube or any cluster)
- kubectl
- Docker

### Commands
```
kubectl create -f postgres-pod.yaml
kubectl create -f postgres-service.yaml

kubectl create -f redis-pod.yaml
kubectl create -f redis-service.yaml

kubectl create -f voting-app-pod.yaml
kubectl create -f voting-app-service.yaml

kubectl create -f worker-app-pod.yaml

kubectl create -f result-app-pod.yaml
kubectl create -f result-app-service.yaml

minikube service voting-service --url
minikube service result-service --url
```

