# k8s
vi firstpod.yml

kind: Pod
apiVersion: v1
metadata:
  name: myfirstpod
spec:
  containers:
    - name: c00
      image: httpd
      ports:
        - containerPort: 80


kubectl apply -f firstpod.yml

kubectl get pods

kubectl get pods -o wide

copy the ip address
curl ipaddress
you will see it works
