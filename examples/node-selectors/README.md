# Node Selectors

This example demonstrates how to use **node selectors** in Kubernetes to control which nodes a pod can be scheduled on based on node labels.

Node selectors allow you to assign a pod to a specific node by matching the pod's requirements with labels that are applied to nodes.

## Files Included

- `node-selector-pod.yaml`: A sample Pod definition that uses a node selector to specify which node the pod should be scheduled on.

## How It Works

1. **Node Selectors**: Nodes are labeled with specific key-value pairs.
2. **Pod Specifications**: Pods specify a **nodeSelector** field to match these labels. Only nodes with the matching labels can schedule the pod.

### Example Label Command

```bash
kubectl label nodes <node-name> size=Large
```

This command adds a label size=Large to the specified node, which matches the pod's nodeSelector.

## Apply the Pod

```bash
kubectl apply -f node-selector-pod.yaml
```

Now, the pod will be scheduled only on nodes that have the size=Large label.

This ensures that the pod is scheduled only on nodes labeled with `size=Large`. 
