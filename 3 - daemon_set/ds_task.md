# DaemonSet Worksheet


__Task 4, step 5: Once you apply the DaemonSet, what happens and why?__

```
when i run <kubectl get pods>, I dont see the nginx-ds pod. because we havent labeled  node to it. 
```

__Task 4, step 7: What happened when you labeled the node and why?__

```
now i can see the pod in running status.The daemonset detect that the noodes label have chaged and deploy the pods to all nodes with matching label.
``
