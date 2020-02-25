FROM centos:centos7

LABEL name="OSG 3.5 Worker Node Client on EL 7"
LABEL build-date="20200128-1035"

RUN yum -y install https://repo.opensciencegrid.org/osg/3.5/osg-3.5-el7-release-latest.rpm \
                   epel-release \
                   yum-plugin-priorities && \
    yum -y install  \
                   osg-oasis \
		cvmfs-config-default \
                   redhat-lsb-core \
                   singularity && \
    yum clean all && \
    rm -rf /var/cache/yum/*

COPY cvmfs_default.local /etc/cvmfs/default.local

# No need to have autofs process running, we mount manually

ENTRYPOINT for DIR in $CVMFS_REPOSITORIES; do mkdir -p /cvmfs/$DIR && mount -t cvmfs $DIR /cvmfs/$DIR; done && \
	sleep infinity
