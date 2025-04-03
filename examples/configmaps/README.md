## 📌 Frequently Used Kubernetes Commands  

### 🛠️ ConfigMaps  
```sh
# Create a ConfigMap from literal values
kubectl create configmap app-config --from-literal=APP_COLOR=blue --from-literal=APP_MODE=prod

# Get details of a ConfigMap
kubectl get configmap app-config -o yaml

# Describe a ConfigMap
kubectl describe configmap app-config

# Delete a ConfigMap
kubectl delete configmap app-config
```