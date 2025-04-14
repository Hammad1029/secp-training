###### intro to cluster ######

# what is kubectl?

# check kubectl
kubectl version

# cluster details
kubectl cluster-info

# check nodes
kubectl get nodes


###### deploying an app ######

# what are pods?
# what are deployments?
# difference?

# deploy hello world application https://hub.docker.com/r/hammad1029/hello-world
kubectl create deployment tutorial --image=hammad1029/hello-world:latest

# verify
kubectl get deployments

# get pods
kubectl get pods

###### exploring the app #####

# why can't we access the app right now?

# view pods
kubectl get pods

# view pod information
kubectl describe pods

# view pod/container logs
kubectl logs $POD_NAME

# start an isnteractive shell inside the pod
kubectl exec -ti $POD_NAME -- bash

# verify that application is running
curl localhost:8000

# exit
exit


###### expose the app #####

# what are services?

# view pods
kubectl get pods

# view services
kubectl get services

# add new service
kubectl expose deployment/tutorial --type="NodePort" --port 8080

# verify
kubectl get services

# shorthand to get port
kubectl get services/tutorial -o go-template='{{(index .spec.ports 0).nodePort}}'

# verify that application is exposed
curl $(ip):$NODE_PORT


##### manual scaling #####

# view deployments
kubectl get rs

# scale up
kubectl scale deployments/tutorial --replicas=6

# verify
kubectl get deployments
kubectl get pods -o wide
kubectl describe deployments/tutorial

# scale down
kubectl scale deployments/tutorial --replicas=4

# verify
kubectl get deployments
kubectl get pods -o wide
kubectl describe deployments/tutorial


##### load balance test #####

# continious hits. notice ip is changing
watch curl url:NODE_PORT

