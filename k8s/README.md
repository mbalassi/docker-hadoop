# Setup on k8s

You can use the following minimalistic setup to submit the Namenode and DataNode Pods and the accompanying Name Service to k8s:

```
kubectl apply -f namenode.yaml
kubectl apply -f name-service.yaml
kubectl apply -f datanode.yaml
``

Note that the Name Service is needed for the Datanode to be able to connect to the Namenode. Now if you wish to port forward the NN UI to localhost you may:

```
kubectl port-forward service/namenode 9870
```

The current implementation does not add a long-running mount point to preserve data between container runs, it is just for dev/test purposes.
