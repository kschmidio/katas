# Launch a microservice test ensemble on kubernetes cluster
## Prerequisites
* Have access an AWS account
* Completed Kata [Create a kubernetes cluster on aws](kubernetes.md)

## Steps
1. Create deployment.yml for nginx
   ```
   apiVersion: apps/v1 # for versions before 1.9.0 use apps/v1beta2
   kind: Deployment
   metadata:
     name: nginx-deployment
   spec:
     selector:
       matchLabels:
         app: nginx
     replicas: 2 # tells deployment to run 2 pods matching the template
     template:
       metadata:
         labels:
           app: nginx
       spec:
         containers:
         - name: nginx
           image: nginx:1.14.2
           ports:
           - containerPort: 80
   ```
2. Create busybox pod
   ```
   apiVersion: v1
   kind: Pod
   metadata:
   name: busybox
   spec:
   containers:
   - name: busybox
       image: busybox
       args:
       - sleep
       - "3600"   
   ```
3. Check that all pods are running
   ```
   kubectl get pods
   ```
4. Log into busybox pod and contact nginx pod
   ```
   kubectl get pods -o wide
   kubectl exec -it busybox sh
   ping <ENTER_NGINX_IP_RETRIEVED_ABOVE>
   wget <ENTER_NGINX_IP_RETRIEVED_ABOVE>
   cat index.html
   ```
