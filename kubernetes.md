### Basic Kubectl Commands

```
kubectl cluster-info                                                                                   # Get info about cluster
kubectl get nodes                                                                                      # Get info about nodes 
kubectl get deployments                                                                                # Get deployments from current namespace
kubectl get pods --all-namespaces                                                                      # Get pods from all namespaces
kubectl get pods -n <namespace>                                                                        # Get pods of specific namespace
kubectl create namespace <namespaceName>                                                               # Create namespace
kubectl delete namespace <namespace>                                                                   # Delete namespace 
kubectl port-forward <podName> 8080:8080                                                               # Forward 8080 port of pod to local machine to access UI
kubectl logs -f <podName>                                                                              # Get logs of pod
kubectl logs -f -c <podName> <containerName>                                                           # Get logs of specific container in the pod
kubectl config set-context $(kubectl config current-context) --namespace=<insert-namespace-name-here>  # Permanently save the namespace for all subsequent commands
kubectl edit configmap <configMap>                                                                     # Edit running configmap on the go
```

### Some more advance commands

```
kubectl api-versions                                                                                   # List of API versions available for current cluster
kubectl proxy                                                                                          # Access kubernetes gui on http://localhost:8001/ui
kubectl delete pod --grace-period=0 --force <podName>                                                  # Force delete pod like in hangig stage
kubectl get pods --selector=app=nginx --output=jsonpath={.items..metadata.name}                        # List pods belonging to rc in a machine readable form
kubectl get pods -o wide                                                                               # Wide output of pods (including nodes that they are running)
kubectl get pods -n team -a                                                                            # Show dead and not visible pods
kubectl rollout history deployment <deployment>                                                        # Show deployment rollout history
kubectl rollout undo deployment <deployment> --to-revision=1                                           # Rollout deployment to 1st revision 
```