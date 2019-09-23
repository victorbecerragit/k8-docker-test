
# Simplre docker deploy on kuberbetes #

#Create git repo for source docker, services and deployment.

$curl -u 'victorbecerragit' https://api.github.com/user/repos -d '{"name":"k8-docker-test"}'

#Sources repo files
'
#Namespace
ns-web1.yaml

#Services
service-web1-nodeport.yaml

#Deployment
deployment.yaml

source docker-hub : https://hub.docker.com/r/victorbecerra/web1
