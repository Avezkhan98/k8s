vi mydeploy.yml

kind: Deployment
apiVersion: apps/v1
metadata:
  name: mydep
spec:
  replicas: 2
  selector:
    matchLabels:
      name: deployment
  template:
    metadata:
      name: testpod
      labels:
        name: deployment
    spec:
      containers:
        - name: c00
          image: ubuntu
          command: ["/bin/bash", "-c","while true; do echo hello world; sleep 5; done"]


kubectl apply -f mydeploy.yml

 kubectl get all
 kubectl get pods
 kubectl get rs
 kubectl get deploy


kubectl get pods
kubectl delete pod <<pod name>>

kubectl get pods
kubectl scale --replicas=5 deploy mydep


NOW WE WILL LAUNCH THE VERSION 2 oF THE PROJECT


vi mydeploy1.yml


kind: Deployment
apiVersion: apps/v1
metadata:
  name: mydep
spec:
  replicas: 2
  selector:
    matchLabels:
      name: deployment
  template:
    metadata:
      name: testpod1
      labels:
        name: deployment
    spec:
      containers:
        - name: c00
          image: ubuntu
          command: ["/bin/bash", "-c","while true; do echo hi i am teaching k8s; sleep 5; done"]


kubectl apply -f mydeploy1.yml
kubectl get pods
kubectl get all
kubectl get rs
kubectl get deploy

kubectl get pods
kubectl logs -f <<pod name which is now created>>

## Roll out

kubectl rollout undo deploy/mydep   (it will rollout to previous version)



kubectl get pods

kubectl logs -f <<pod name which is now created>>

you will see the output of the previous pods . 

