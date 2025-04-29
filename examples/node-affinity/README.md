# Node Affinity

This example shows how to use **node affinity** in Kubernetes to control where a pod can be scheduled based on node labels, with more flexible matching rules than `nodeSelector`.

## Files Included

- `node-affinity-pod.yaml`: A sample Pod definition using node affinity to avoid nodes labeled `size=Small`.
- (You can create a preferred version by replacing `requiredDuringSchedulingIgnoredDuringExecution` with `preferredDuringSchedulingIgnoredDuringExecution`.)

## What Is Node Affinity?

Node affinity is a set of rules that determine on which nodes a pod is eligible to run, based on labels on the nodes.

There are two types of node affinity:

### 1. `requiredDuringSchedulingIgnoredDuringExecution`
- This is a hard rule: the scheduler must place the pod on a node that matches the defined affinity.
- If no such node exists, the pod will remain unscheduled.
- Used when correct placement is critical (e.g., requiring a certain hardware spec).

**Example use case:** You don’t want the pod to run at all unless it's on a specific type of node.

### 2. `preferredDuringSchedulingIgnoredDuringExecution`
- This is a soft rule: the scheduler will try to place the pod on a matching node, but it’s not mandatory.
- If no matching node is found, the pod will still be scheduled on any available node.
- Used when placement is ideal but not critical.

**Example use case:** "Try to put me on this kind of node, but if you can’t, just run me anywhere."

## How It Works

1. **Node Affinity** allows you to define rules about which nodes are eligible for scheduling based on node labels.
2. This example uses `requiredDuringSchedulingIgnoredDuringExecution`, which means:
   - The pod will **only be scheduled** on nodes that do **not** have `size=Small`.
   - Once scheduled, it **won’t be evicted** even if node labels change later.

### Example Label Command

```bash
kubectl label nodes <node-name> size=Small
```

This adds a size=Small label to a node—our pod will avoid being scheduled on such nodes.

Apply the Pod
```bash
kubectl apply -f node-affinity-pod.yaml
```

```bash
kubectl create -f node-affinity-pod.yaml
```

Now, the pod will only be scheduled on nodes where size is not Small.
