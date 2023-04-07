# StatefulSet Worksheet

__Task 5, step 3: Describe what happened and what you noticed about the pods and the volumes for them.__

```
when statefulset controooller creates a pod, it adds a label,ubernetes.io/pod-name, that is set to the name of the pod. This label allows you to attach a service to specific pod in the statefulset. and each Pod receives one PersistentVolumeClaim


```

__Task 5, step 4: Did anything change? Why or why not?__

```
Nothing change because the statefulset's spec.updateStrategy.type is set to OnDelete.which will not automatically update the Pods in satefulset.they need to manually delete pods to cause the controller to create new pods to reflect the changes.
```

__Task 5, step 6: What happened and why?__

```
Now i deleted pod 0, the controller create new pods that reflect modification made to statefulsets .spec.template. i.e  stateful-nginx-0 is now ruuunning in version 2.0

```

__Task 5, step 9: What happens this time?__

```
We changed .spec.updateStrategy.type to RollingUpdate, which automatically deleted and recreated each of 3 pods in version 3.0
```

__Task 5, step 11: Repeat step 10. Was everything deleted? Why or why not?__

```
Only the satefulset is deleted.That is the limitation of statefulsets that it doesnot provide any guaranrees on the termination of pods when a statefulset is deleted.same with the volumes associated with the statefulset
``
