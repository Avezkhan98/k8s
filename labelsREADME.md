vi labels.yml

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
