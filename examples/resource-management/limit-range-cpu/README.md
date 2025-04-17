# Limit Range - CPU

This example defines a `LimitRange` for CPU resources within a specific Kubernetes namespace.

## What It Does

- Sets default CPU **request and limit** to `500m`.
- Ensures a **minimum CPU request** of `100m`.
- Prevents containers from requesting more than **1 vCPU**.

## Why Use It

Guarantees fair CPU usage and prevents containers from consuming excessive

## Apply the YAML

```bash
kubectl apply -f limit-range-cpu.yaml -n your-namespace
```

Replace your-namespace with your actual namespace.