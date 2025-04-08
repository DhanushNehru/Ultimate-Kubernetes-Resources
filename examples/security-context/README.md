# Security Context

### pod-with-user.yaml
A pod that runs as a specific non-root user (`runAsUser: 1000`).

### pod-with-capabilities.yaml
A pod that adds the MAC_ADMIN Linux capability for enhanced permissions.

### Some useful commands 
```sh
# Apply a security context pod
kubectl apply -f pod-with-user.yaml

# Verify security context applied
kubectl describe pod web-pod

# Delete the pod
kubectl delete pod web-pod
```