# Docker containers for CernVM-FS client

For examples on how to use them and documentation refer to [`zonca/jupyterhub-deploy-kubernetes-jetstream` repository](https://github.com/zonca/jupyterhub-deploy-kubernetes-jetstream/tree/master/cvmfs)

## Prerequisites

* Run the container in **privileged** mode

## Available containers

* `cvmfs-client`: cvmfs client preconfigured for CDMS, available as [zonca/cvmfs-client](https://hub.docker.com/repository/docker/zonca/cvmfs-client) on DockerHub
* `cvmfs-client-nfs`: cvmfs client preconfigured for CDMS, with NFS server to share with other clients available as [zonca/cvmfs-client-nfs](https://hub.docker.com/repository/docker/zonca/cvmfs-client-nfs) on DockerHub
