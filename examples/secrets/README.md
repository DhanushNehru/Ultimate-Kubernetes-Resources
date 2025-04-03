## 📌 Frequently Used Kubernetes Commands  

### 🛠️ Secrets  
```sh
# Create a Secret from a file
kubectl create secret generic app-secret --from-file=secret.yaml

# Create a Secret from literal values
kubectl create secret generic app-secret --from-literal=DB_Host=mysql --from-literal=DB_User=root --from-literal=DB_Password=yourpassword

# Get details of a Secret (Base64 encoded)
kubectl get secret app-secret -o yaml

# Describe a Secret
kubectl describe secret app-secret

# Delete a Secret
kubectl delete secret app-secret
```