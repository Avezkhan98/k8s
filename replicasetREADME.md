vi replicaset.yml

apiVersion: apps/v1
kind: ReplicaSet   #Creating replicaSet
metadata:
  name: replicaakshat  #name of replicaset
spec:
  replicas: 5   #we are creating 5 replicas
  selector:
    matchLabels:
      myname: akshat  #which should match the source pod with label myname: ashok
  template:
     metadata:
        name: templateforreplica   # the name of the source pod
        labels:
         myname: akshat    #this is the label of source pod. it shoudl match the selector above
     spec:
       containers:
          - name: php-redis
            image: nginx


kubectl apply -f replicaset.yml

kubectl get pods -o wide
