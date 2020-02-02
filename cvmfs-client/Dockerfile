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

ENTRYPOINT mkdir -p /cvmfs/config-osg.opensciencegrid.org && \
	mount -t cvmfs config-osg.opensciencegrid.org /cvmfs/config-osg.opensciencegrid.org && \
	mkdir -p /cvmfs/cdms.opensciencegrid.org && \
	mount -t cvmfs cdms.opensciencegrid.org /cvmfs/cdms.opensciencegrid.org && \
	sleep infinity
