multicontainer pod.yml


kind: Pod
apiVersion: v1
metadata:
  name: mymulticontpod
spec:
  containers:
    - name: c00
      image: httpd
      ports:
        - containerPort: 80

    - name: c01
      images: ubuntu
      command: ["/bin/bash" , "-c" , "while true: do echo hello world ; sleep 300" , done"]
       port: 
        - containerPort : 90
             
