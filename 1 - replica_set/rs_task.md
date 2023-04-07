# ReplicaSet Worksheet:

__Task 1, step 7: Enter the command you used for scaling the replica set:__
```
kubectl scale rs/nginx-replica --replicas=3
```

__Task 1, step 9: What happened after applying another pod with matching selectors as the ReplicaSet?__
```
Result from kubectl describe rs nginx-replica

Name:         nginx-replica
Namespace:    default
Selector:     app_name=nginx,env=dev
Labels:       <none>
Annotations:  <none>
Replicas:     3 current / 3 desired
Pods Status:  3 Running / 0 Waiting / 0 Succeeded / 0 Failed
Pod Template:
  Labels:  app_name=nginx
           env=dev
  Containers:
   nginx:
    Image:        nginx:stable-alpine
    Port:         80/TCP
    Host Port:    0/TCP
    Environment:  <none>
    Mounts:       <none>
  Volumes:        <none>
Events:
  Type    Reason            Age    From                   Message
  ----    ------            ----   ----                   -------
  Normal  SuccessfulCreate  14m    replicaset-controller  Created pod: nginx-replica-27xlm
  Normal  SuccessfulCreate  14m    replicaset-controller  Created pod: nginx-replica-xb9xp
  Normal  SuccessfulCreate  5m13s  replicaset-controller  Created pod: nginx-replica-mx8rd
  Normal  SuccessfulDelete  3m39s  replicaset-controller  Deleted pod: nginx-pod


so  the latest one is terminated since there's a specific numbers of replicas (which is 3 in this case) already running for matching selectors.
