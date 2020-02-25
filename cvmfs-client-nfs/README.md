# Docker container for CernVM-FS client with NFS server

* CentOS 7
* Installs `osg-oasis` to provide the CVMFS client
* Manually mounts the CVMFS repositories defined in `CVMFS_REPOSITORIES` files to `/cvmfs/`
* Shares CVMFS folders through NFS
