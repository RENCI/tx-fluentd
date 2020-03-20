# tx-fluentd
## purpose
Creates a container on the extant fluentd image, setting up a mongodb container (see Dockerfile and etc/fluent.conf) using the environmental variables:
* MONGO_NON_ROOT_USERNAME, MONGO_NON_ROOT_PASSWORD - for authenticating the external mongodb container
* MONGO_HOST -  Set MONGO_HOST to the name of the mongodb container. 
* MONGO_COLLECTION, FLUENTD_APP are unique names that the tx-fluentd client invents for the purpose of uniquely identifying this logging service.

## examples:
* tx-logging - Currently this repo can be used to create a container to support containers created by the tx-logging repo.

* tx-persistence - If using tx-persistence for the mongodb, use the same username and password environmental variables to initialize both the tx-persistent and tx-fluentd containers. The MONGO_DATABASE environmental variable used to deploy tx-fluentd should match the MONGO_INITDB_DATABASE environmental variable value used for spinning up the tx-persistence container. MONGO_HOST for tx-persistence, for example, might be "tx-persistence", depending on the service name in the docker-compose file. 
