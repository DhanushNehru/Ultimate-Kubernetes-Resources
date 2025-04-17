# Limit Range - Memory

This example defines a `LimitRange` for memory resources within a Kubernetes namespace.

## What It Does

- Sets default memory **request and limit** to `512Mi`.
- Enforces a **minimum request** of `128Mi`.
- Prevents containers from requesting more than **1Gi** of memory.

## Why Use It

Helps ensure that containers don’t over-consume memory resources in a shared environment.  
By defining defaults and boundaries, it encourages developers to write resource-conscious applications and prevents accidental memory hogging.

## Apply the YAML

```bash
kubectl apply -f limit-range-memory.yaml -n your-namespace
```

Replace your-namespace with the actual namespace you're applying it to.