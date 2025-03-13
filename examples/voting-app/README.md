# voting-app ( Deploying Microservices Application on Kubernetes )
This repository contains Kubernetes configuration files to deploy a complete Voting App setup using individual Pods. 
The application consists of the following components:

- Postgres Pod: Stores voting data.
- Redis Pod: Acts as a queue for votes.
- Voting App Pod: Frontend for users to cast their votes.
- Worker App Pod: Processes votes from Redis and stores them in Postgres.
- Result App Pod: Displays voting results.

### Prerequisites
Make sure you have the following installed:

- Kubernetes (minikube or any cluster)
- kubectl
- Docker

### Commands
```bash
kubectl create -f postgres-pod.yaml
kubectl create -f postgres-service.yaml

kubectl create -f redis-pod.yaml
kubectl create -f redis-service.yaml

kubectl create -f voting-app-pod.yaml
kubectl create -f voting-app-service.yaml

kubectl create -f worker-app-pod.yaml

kubectl create -f result-app-pod.yaml
kubectl create -f result-app-service.yaml

kubect get all # Check that 5 pods and 4 services (db, redis, result, voting) are running

# Get the external URL to access the Voting App through Minikube
minikube service voting-service --url
# Get the external URL to access the Result App through Minikube
minikube service result-service --url
```

