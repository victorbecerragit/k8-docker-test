
# Simplre docker deploy on kuberbetes #

#Create git repo for source docker, services and deployment.

$curl -u 'victorbecerragit' https://api.github.com/user/repos -d '{"name":"k8-docker-test"}'

#Sources repo files

#Namespace

ns-web1.yaml

#Services

service-web1-nodeport.yaml

#Deployment

deployment.yaml

source docker-hub : https://hub.docker.com/r/victorbecerra/web1

#Deploy on kubernets
#Create namespace

kubectl apply  -f https://raw.githubusercontent.com/victorbecerragit/k8-docker-test/master/ns-web1.yaml

#Create service , selector and port

kubectl create -f https://raw.githubusercontent.com/victorbecerragit/k8-docker-test/master/service-web1-nodeport.yaml

#check services created in your namespaces

kubectl get svc -n web1-site

#Create the container with his replicas

kubectl create -f https://raw.githubusercontent.com/victorbecerragit/k8-docker-test/master/deployment.yaml

#Check deployments in your namespace

kubectl get deployments -n web1-site -o wide

