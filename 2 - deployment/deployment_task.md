# Deployment Worksheet

__Task 2, step 6: After completing step 5 of task 2, what do you notice about the `ReplicaSet` - what is this used for?__
hint: use ` kubectcl get rs --show-labels`

```
Noticed that the labels are added for pod-template-hash=65d8798d86 and the name of the replica set is in the format of <NameOfDeployment>-< value of pod-template-hash>
This ensures that child replicasets of deployment do not overlap.
```

__Task 2, step 7: what command did you use to scale the deployment?__

```
kubectl scale deployment/nginx-deployment --replicas=3
```

__Task 3, step 2: Why are there two replica sets but only one deployment?__

 ```
So the deployment controller seems to bring up the desired pods everytime a new deployment object is obsserved with a desired replica set. if it found a existinng replica set whose lables match but whose template doesnot match it will scaled down.Eventually, the new Replica Set will be scaled to .spec.replicas and all old Replica Sets will be scaled to 0.


```

__Task 3, step 6: What command did you use to roll back the deployment?__

```
kubectl rollout history deployment/nginx-deployment --revision=1

```

