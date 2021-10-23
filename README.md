# Kubernetes Final Homework

## Working with YAML/YML files to create a webpage for spring music application:
To use the application 'spring music' on your localhost you will need to follow these simple steps:
1) clone all 3 YAML files to your computer (preferrably visual studio code)
2) apply the cloned YAML files in your terminal using the command: 'kubectl apply -f deployment.yaml' 'kubectl apply -f service.yaml' 
3) you can check if your pods are currently running by using the 'kubectl get pods -owide' command, and check out the status, it should say running.
4) you can use the 'kubectl describe service spring-music-service' and check the end point of the command, it should match the ip of the pod we checked in the previous step.
5) after we checked steps 3 and 4, the service is now available for us here: http://localhost:8080/

### Scaling replicas:
to create a number of pods we can do that in 2 different ways:
1) in the yaml file we can specify the number of pods we would like to create
2) use the command kubectl scale --replicas=2 deployment spring-music-deployment

## Accessing the application through http://127.0.0.1/music :
To do so we need to work with the ingress.yaml file:
there is some preprocessing that needs to be done prior to using the ingress.yaml file, which is installing the ingress controller, you can find the instructions here:
https://kubernetes.github.io/ingress-nginx/deploy/#docker-desktop
after installation, we can work with the ingress.yaml file:
1) clone the ingress.yaml file to your computer or just copy the code to your visual studio code
2) use command 'kubectl apply -f ingress.yaml'
3) verify that the command succeeded by using 'kubectl get ingress' and checking if you have a 'spring-music-ingress' running.
4) you are all set! access the application here: http://127.0.0.1/music

you should be redirected to this page:

![image](https://user-images.githubusercontent.com/91056755/138536607-e5828112-103f-4b4a-a18f-4b2bee9851d1.png)

hope you found this tutorial helpful :)
