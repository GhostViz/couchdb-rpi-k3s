# couchdb-rpi-k3s

This deployment utilizes the [treehouses/couchdb](https://hub.docker.com/r/treehouses/couchdb) image from dockerhub to set up a single instance of couchdb.

## How to Use

1. Clone the repository 
``` Shell
git clone git@github.com:oxhankey/couchdb-rpi-k3s.git
```
2. Update the deployment environment variables
3. Create the CouchDB Deployment
``` Shell
kubectl create -f couchdb-rpi-k3s/couchdb-deployment.yaml
```
4. Create the CouchDB Service
``` Shell
kubectl expose deployment couchdb-deployment --type=NodePort --name=couchdb-service 
```
or
``` Shell
kubectl create -f couchdb-rpi-k3s/couchdb-service-nodeport.yaml
```

## Disclaimer
This should not be used for any sort of sensitive information or production environment in it's current state. 

## Future Updates
TLS for couchdb communication
couchdb clustering across multiple pods
