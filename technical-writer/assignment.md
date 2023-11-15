# Operations in Kubernetes

Kubernetes contains several commands used to perform tasks. The CLI used to communicate with Kubernetes is `kubectl`. The `kubectl` CLI commmunicates with the Kubernettes API server. 

 
The following is a list of helpful `kubectl` commands:
- `kubectl get pods`: Provides a list of all pods available and their current status. When you use this command, specify the `namespace` if required.
- `kubectl logs`: Used to retrive the logs of a specific pod  In Azure, Kubernetess is available, just like other Cloud Providers. Use this when you have to review logs or need to debug a container.  
- `kubectl exec`: Used to debug a container from the inside or to explore the enviroment of the container itself.  

For debugging, begin with `kubectl get pods` followed by `kubectl logs` and finally `kubectl exec` to explore the inside of the container and review other log files or configurations. 

Example:
```shell
kubectl get pods --namespace 
```
```shell
kubectl logs
```
```shell
kubectl exec 
```


**Note:** The command `kubectl debug` is another option to considering when debugging a container. This command is used to create a clone of a pod that does not terminate if an error is experienced inside the container. 



# References

- [Kubectl Commands](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#-strong-getting-started-strong-)

- [What is Kubernetes](https://kubernetes.io/docs/concepts/overview/)
