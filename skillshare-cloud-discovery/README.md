# skillshare-cloud-discovery

Pre-requisites:
--------
    - Install Git
    - Install Maven
    - Install Docker
    - EKS Cluster
    
Clone code from github:
-------
    git clone https://github.com/krishnajha99/skillshare-cloud-kubernetes.git
    cd skillshare-cloud-kubernetes/skillshare-cloud-discovery
    
Build Maven Artifact:
-------
    mvn clean install
 
Build Docker image for skillshare api
--------------
    docker build -t krishnajha99/skillshare-cloud-discovery .
  
Docker login
-------------
    docker login
    
Push docker image to dockerhub
-----------
    docker push krishnajha99/skillshare-cloud-discovery
    
Deploy skillshare Application:
--------
    kubectl apply -f deployment.yaml
    
Check Deployments, Pods and Services:
-------

    kubectl get deploy
    kubectl get pods
    kubectl get svc
    
Now Goto Loadbalancer and check whether service comes Inservice or not, If it comes Inservice copy DNS Name of Loadbalancer and Give in WebUI
    
    http://xxxxxxxxxxxxxxxxxxxxxx.elb.amazonaws.com:8081/api/sample

Now we can cleanup by using below commands:
--------
    kubectl delete deploy skillshare-cloud-discovery
    kubectl delete svc skillshare-cloud-discovery
