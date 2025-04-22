# Taints and Tolerations

This example demonstrates how to use **taints** and **tolerations** in Kubernetes to control which pods can be scheduled on specific nodes.

Taints are used to mark a node so that only certain pods can be scheduled on it.
Tolerations are added to pods to let them run on tainted nodes.
This helps control which pods go where in your cluster.

## Files Included

- `toleration-pod.yaml`: A sample Pod definition with tolerations that allow it to run on tainted nodes.

## How It Works

1. **Taints** are applied to nodes to repel pods that do not tolerate them.
2. **Tolerations** are added to pod specs, allowing them to be scheduled on nodes with matching taints.

### Example Taint Command

```bash
kubectl taint nodes <node-name> example-key=example-value:NoSchedule
```

This command prevents all pods without a matching toleration from being scheduled on the node.

### Apply the Pod

```bash
kubectl apply -f toleration-pod.yaml
```