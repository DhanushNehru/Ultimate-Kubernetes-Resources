# voting-app ( Deploying Microservices Application on Kubernetes with Deployments )
This repository contains Kubernetes configuration files to deploy a complete Voting App setup using Deployments for better scalability and management. 
The application consists of the following components:

- Postgres Deployment: Manages database instances for vote storage.
- Redis Deployment: Manages Redis instances as a vote queue.
- Voting App Deployment: Frontend service where users cast their votes.
- Worker App Deployment: Processes votes and updates the database.
- Result App Deployment: Shows voting results in real-time.

### Prerequisites
Make sure you have the following installed:

- Kubernetes (minikube or any cluster)
- kubectl
- Docker

### Commands
```bash
kubectl create -f postgres-deploy.yaml 
kubectl create -f postgres-service.yaml

kubectl create -f redis-deploy.yaml 
kubectl create -f redis-service.yaml

kubectl create -f voting-app-deploy.yaml 
kubectl create -f voting-app-service.yaml

kubectl create -f worker-app-deploy.yaml

kubectl create -f result-app-deploy.yaml 
kubectl create -f result-app-service.yaml

kubect get all # Check that 5 pods and 4 services (db, redis, result, voting) are running

# Get the external URL to access the Voting App through Minikube
minikube service voting-service --url
# Get the external URL to access the Result App through Minikube
minikube service result-service --url
```