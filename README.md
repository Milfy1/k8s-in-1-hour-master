#### where to start?
I recommend watching Kubernetes Crash Course for Absolute Beginners [NEW]
https://www.youtube.com/watch?v=s_o8dwzRlu4&ab_channel=TechWorldwithNana

this assignment is the same as the demo project found in the above video.

first of all, you need to install both:

1- Docker
2- minikube

then you can run this command:
* minikube start --driver docker 


### as for the yaml files, you can create them using CLI or as files in a project like this one. 
there are four yaml files:

* mongo-config.yaml : for setting the needed configuration and map them so that you can edit in one place.
* mongo-secret.yaml : here you can save and encrypt you secret or confidentail data.
* mongo.yaml : yaml file for the DB including the service yaml file. 
* webapp.yaml : yaml file for the app including the service yaml file.

the services enables pods to communicate with each other.

last but not least, you need to access your yaml files and run them by running this command for each yaml file:

* kubectl apply -f ${yourYamlFile} 

when it is up and running, run this command and a webpage will pop up with your project:

* minikube service webapp-service


### Repository for the K8s in 1 hour video

#### K8s manifest files 
* mongo-config.yaml
* mongo-secret.yaml
* mongo.yaml
* webapp.yaml

#### K8s commands

##### start Minikube and check status
    minikube start --vm-driver=hyperkit 
    minikube status

##### get minikube node's ip address
    minikube ip

##### get basic info about k8s components
    kubectl get node
    kubectl get pod
    kubectl get svc
    kubectl get all

##### get extended info about components
    kubectl get pod -o wide
    kubectl get node -o wide

##### get detailed info about a specific component
    kubectl describe svc {svc-name}
    kubectl describe pod {pod-name}

##### get application logs
    kubectl logs {pod-name}
    
##### stop your Minikube cluster
    minikube stop

<br />

> :warning: **Known issue - Minikube IP not accessible** 

If you can't access the NodePort service webapp with `MinikubeIP:NodePort`, execute the following command:
    
    minikube service webapp-service

<br />

#### Links
* mongodb image on Docker Hub: https://hub.docker.com/_/mongo
* webapp image on Docker Hub: https://hub.docker.com/repository/docker/nanajanashia/k8s-demo-app
* k8s official documentation: https://kubernetes.io/docs/home/
* webapp code repo: https://gitlab.com/nanuchi/developing-with-docker/-/tree/feature/k8s-in-hour

####

* for more details you can watch https://www.youtube.com/watch?v=s_o8dwzRlu4&ab_channel=TechWorldwithNana

