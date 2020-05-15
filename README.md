# Tomcat-Kubernetes

Pre-requisites:
--------
    - Install Git
    - Install Maven
    - Install Docker
    - EKS Cluster
    
Clone code from github:
-------
    git clone https://github.com/Naresh240/tomcat-kubernetes.git
    cd tomcat-mavewebappdemo
    
Build Maven Artifact:
-------
    mvn clean install
 
Build Docker image for Springboot Application
--------------
    docker build -t naresh240/tomcat-kubernetes .
  
Docker login
-------------
    docker login
    
Push docker image to dockerhub
-----------
    docker push naresh240/tomcat-kubernetes
    
Deplot Tomcat application
------
    kubectl apply -f tomcat-deploy.yml
    kubectl apply -f tomcat-service.yml
    
Now Goto Loadbalancer and check whether service comes Inservice or not, If it comes Inservice copy DNS Name of Loadbalancer and check in web UI 

    http://af95d195f45b744edbf46cc7a41b1f91-1347812778.us-west-2.elb.amazonaws.com/mavewebappdemo
    
