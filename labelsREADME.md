i labels.yml

kind: Pod
apiVersion: v1
metadata:
  name: testlabel
  labels:
    env: preprod
    name: akshat
spec:
  containers:
    - name: c00
      image: ubuntu
      command: ["/bin/bash", "-c", "while true; do echo welcome; sleep 50; done"]


     kubectl apply -f labels.yml
     kubectl get pods
     kubectl get pods -o wide
     kubectl get pods -o wide --show-labels
     kubectl get pods --show-labels
     kubectl label pod testpod env=prod name=john age=70    #labeling the existing pods which does not have labels 
     kubectl get pods --show-labels
     kubectl get pods -l env=preprod
     kubectl get pods -l env=prod
