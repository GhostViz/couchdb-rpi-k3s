# couchdb-rpi-k3s

This deployment utilizes the [treehouses/couchdb](https://hub.docker.com/r/treehouses/couchdb) image from dockerhub to set up a single instance of couchdb.

COUCHDB_USER and COUCHDB_PASSWORD can be set in the deployment file to be passed as environment variables. 

To load couchdb into your k3s cluster you will first run `kubectl create -f couchdb-deployment.yaml`.

Once your couchdb pod is running expose the deployment via NodePort by either using

`kubectl expose deployment couchdb-deployment --type=NodePort --name=couchdb-service` 
or 
`kubectl create -f couchdb-service-nodeport.yaml`


Disclaimer:
This should not be used for any sort of sensitive information or production environment in it's current state. 

Known Issues / Planned Fixes:
TLS for couchdb communication
couchdb clustering across multiple pods
