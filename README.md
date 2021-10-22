# Kubernetes Ingress-Closing task

In this task we'll create a deployment & a service for the:`yanivomc/spring-music:latest ` image .




## ✨Deploy the image:

>The Deployment file is called SmusicDep.yaml,that exposes the deploy using type = ClusterIP and with port 8090:8080.

 - Run the deployment using :
```sh
kubectl apply -f SmusicDep.yaml
```
- Check that you've created a pod :
```sh
kubectl get pods 
```
>you'll see the pod name with the status running and the age of a few secounds because you've just created it .

- Verify that the service is deployed :
```sh
kubectl get svc 
```
> you'll see the service name and the type ClusterIP with the port(s) 8090/TCP.

- Once Exposed and verified scale your pods to 2 :
```sh
kubectl scale --replicas=2 deployment spring-music
```
- Install the nginx ingress-controller in your cluster, follow
instructions in this link
https://kubernetes.github.io/ingress-nginx/deploy/#docker-desktop 

- when you're done, check you're installation :
```sh
kubectl get pods -n ingress-nginx
```

- Run the Ingress.yaml file:
>this file is responsiple for defining the path : /music with port 8090.
```sh
kubectl apply -f ingress.yaml
```
- Now you can access the service using the URL: 
http://127.0.0.1/music 
 you can access the app using : http://localhost:1999/  .

![Screenshot](https://github.com/SewarDarawshe/K8s_Ingress_FinalTask/blob/main/4.png)




