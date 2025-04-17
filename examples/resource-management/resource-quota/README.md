# Resource Quota

This example defines a `ResourceQuota` for a Kubernetes namespace to control overall resource usage.

## What It Does

- Limits the total **CPU requests** to `4` and **CPU limits** to `10`.
- Limits the total **memory requests** to `4Gi` and **memory limits** to `10Gi`.
- Applies to all pods in the specified namespace.

## Why Use It

Useful in multi-tenant clusters or shared environments where you want to:

- Prevent a single team or app from consuming all the resources.
- Ensure predictable performance by enforcing resource boundaries.
- Apply cluster-wide governance and policies.

## Apply the YAML

```bash
kubectl apply -f resource-quota.yaml -n your-namespace
```

Replace your-namespace with your actual namespace name.