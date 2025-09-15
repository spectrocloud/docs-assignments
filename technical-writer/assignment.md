# Debug Operations in Kubernetes

## Before You Begin 
- Your Pod should already be scheduled and running. If your Pod is not running, start with [Debugging Pods](https://kubernetes.io/docs/tasks/debug/debug-application/).
- For some advanced debugging steps, you will need to know on which Node the Pod is running and have shell access to run commands on that Node. 


## Viewing Pods and Nodes
      
To view a Pod or Node, you can use the Kubernetes Command Line Interface (CLI) to run the following command: 

```shell
    kubectl get pods
```    

This will list all the Pods that are available and their status.  

To see the information for a specific Pod, you can add the namespace parameter to the command: 

```shell
    kubectl get pods --namespace
```


## Viewing Logs of a Pod 
To view the logs of a specific Pod, you can use the CLI to run the following command: 

```shell
    kubectl logs
```
The above command is used to retrieve the logs of a specific Pod. 
The [-c CONTAINER] parameter can be used if there is more than one container. 
You can use this command when you have to debug a container. 



## Running Commands Inside a Running Container 
When you need to interact with a container running in your cluster—whether to troubleshoot, check logs, test commands, or manually fix a process — `kubectl exec` gives you a way to do it interactively. It is similar to using `ssh` on a VM, but for containers in Kubernetes. You can use the CLI to run this command: 

```shell
    kubectl exec
```


## Debugging a Container
If you need to debug the container, you can use `kubectl debug` to use automated debugging tasks to learn what needs to be fixed. You can use this command to create a clone of the Pod that will keep running even if there is an error in the container. You can use the CLI to run this command: 

```shell
    kubectl debug 
```


## Debugging Best Practices 
- **Keep logs and events:** Logs and events are valuable sources of information when debugging Kubernetes clusters. It is important to keep logs for a sufficient period of time and to store them in a central location for easy access.
- **Use descriptive and meaningful labels:** Labels can be used to categorize and identify resources in a Kubernetes cluster. Using descriptive and meaningful labels can make it easier to find the resources you are looking for when debugging.
- **Monitor resource usage:** Monitoring resource usage can help identify performance bottlenecks and resource constraints in the cluster. This information can be used to diagnose issues and to make adjustments to the cluster configuration.


# See Also 

- [Debug Running Pods](https://kubernetes.io/docs/tasks/debug/debug-application/debug-running-pod/)

- [kubectl get pods](https://kubernetes.io/docs/tutorials/kubernetes-basics/explore/explore-intro/)

- [kubectl logs](https://kubernetes.io/docs/reference/kubectl/generated/kubectl_logs/)

- [kubectl exec](https://kubernetes.io/docs/reference/kubectl/generated/kubectl_exec/)


# Feedback 
Was this page helpful? 

| Yes | No |