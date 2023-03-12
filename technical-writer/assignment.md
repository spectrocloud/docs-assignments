
<img title="k8s" alt="k8s" src="/technical-writer/k8s.png">
Ashley McNamara, 2017.

# Debug Operations in Kubernetes

## Overview

It is essential to understand how to debug efficiently in Kubernetes. Overlapping complexities when debugging enhances the efficiency and end-user experience. 
You can use the respective command operations based on the debugging user case when you understand how to debug Kubernetes resources effectively. 




## Commands to Debug Resources

Kubernetes contains several command operations which you can use based on your debugging needs. You can run command operations for troubleshooting on either cluster-level or application-based debugging. 

For debugging operations, the kubectl command CLI interacts with k8s. It communicates with the Kubernetes API server. 

<img title="k8s" alt="k8s" src="/technical-writer/luster.png">

### Cluster Level Troubleshooting

Kubernetes cluster can detect issues when a component(s) in the cluster has any problem. 
Some critical command operations to run in such cases are: 
    
1. **kubectl get nodes**
    Run the following command to verify if your nodes are registered correctly.
    This command allows you to check the status of a node to verify if it is unhealthy or affecting your Kubernetes cluster. You will find the name, status, roles, age and the Kubernetes version running the node. 
    `kubectl get nodes`
<br>

2. **kubectl cluster-info**
    Run the following command to obtain information about the components of your Kubernetes cluster. Using this command, you can check the information on the status of the cluster’s control plane and the CoreDNS. 
    `kubectl cluster-info`

!!! Info Use this command for output information about your cluster and its activities:`kubectl cluster-info dump`

### Application-Based Troubleshooting

Assessing and debugging applications arise when your cluster and node are healthy, but there are issues within the pod or the container. In such cases, you have to verify the issues against the containerised applications as a way to debug. 

1. **Pod**

    - **kubectl get pods**
This command lists all the pods in namespace. 
`kubectl get pods`

    - **kubectl describe pod** 
Run the following command to view a detailed summary of your pod and their status. 
`kubectl describe pod`

    !!! Note: After you run the `kubectl get pods` command, and the status of the pod shows otherwise, instead of running, this command will help to identify the root of the issue.


    - **kubectl get logs**
This command retrieves the logs of a specific pod. You can run this to review logs or to debug a container. 
`kubectl get logs`

    !!! Note: You can debug with the `kubectl get pods` command first, then run the `kubectl get logs.`

2. **Container**

    - **kubectl exec**
This command helps debug a container from the inside or explore the container’s environment. 
`kubectl exec`

    - **kubectl debug mypod**
This command is another option to consider when debugging a container. 
You can run the command to create a clone of a pod that does not terminate if there is an error inside the container.
`kubectl debug mypod`



# References

- [Ashley McNamara,2017](https://medium.com/over-engineering/graceful-shutdown-with-go-http-servers-and-kubernetes-rolling-updates-6697e7db17cf)

- https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#-strong-getting-started-strong-

- [What is Kubernetes](https://kubernetes.io/docs/concepts/overview/)
