# Debug Commands

The `kubectl` command-line interface (CLI) allows containers to be debugged by accessing a cluster's [control plane](https://kubernetes.io/docs/reference/glossary/?all=true#term-control-plane) through the Kubernetes API.
The control plane returns information about container lifecycles, which is then used for troubleshooting the cluster.

Debugging combines several operations to retrieve information and test from the inside. 
The official Kubernetes [debugging guide](https://kubernetes.io/docs/tasks/debug/) offers a deeper dive into troubleshooting beyond this document's scope.


## Retrieve Information

Run `kubectl get pods` to return a list of all pods in the current namespace.
Provide a `--namespace` to retrieve information about pods in a given namespace, or use `--all-namespaces` to list all pods in all namespaces.

```shell
kubectl get pods
```

```
NAME          READY   STATUS       RESTARTS        AGE
examplepod1   1/1     Completed    1 (12s ago)     42s
examplepod2   0/1     Waiting      0               2m21s
```

Retrieve recent events from all pods with `kubectl describe pods`. 
A pattern of events, along with logs from the pod, can be reviewed together while debugging a container.

Retrieve the pod logs with `kubectl logs`.
Provide a pod name, or fetch logs for all pods with `--all-pods`.


## Debug Container

Debugging a container can be achieved through two commands: `kubectl exec` and `kubectl debug`.

Use `kubectl exec` to execute commands on an existing pod.
This allows for exploration and testing through an interactive shell, making it great for simple troubleshooting cases.
However, caution must be taken to avoid modifying other containers or pods.

For scenarios requiring extensive pod access, use `kubectl debug`.
This feature, introduced in Kubernetes version 1.18, creates a new container that connects to a running pod.
Neither the application, nor container images, are modified when using this command.
Once debugging is complete, the container can be disposed of without affecting the rest of the cluster.


# References

- [Command line tool (kubectl)](https://kubernetes.io/docs/reference/kubectl/)

- [Debugging Running Pods on Kubernetes](https://medium.com/datamindedbe/debugging-running-pods-on-kubernetes-2ba160c47ef5)
  
- [How to Get Pod Logs in Kubernetes](https://kodekloud.com/blog/kubectl-logs/)

- [Logs](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#logs)

- [Overview](https://kubernetes.io/docs/concepts/overview/)

- [Pods](https://kubernetes.io/docs/concepts/workloads/pods/)

