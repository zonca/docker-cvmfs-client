FROM centos:centos7

LABEL name="OSG 3.5 Worker Node Client on EL 7"
LABEL build-date="20200128-1035"

RUN yum -y install https://repo.opensciencegrid.org/osg/3.5/osg-3.5-el7-release-latest.rpm \
                   epel-release \
                   yum-plugin-priorities && \
    yum -y install  \
                   unzip \
                   osg-oasis \
		cvmfs-config-default \
                   redhat-lsb-core \
                   singularity && \
    yum clean all && \
    rm -rf /var/cache/yum/* && \
    curl -O https://downloads.rclone.org/rclone-current-linux-amd64.zip && \
    unzip rclone-current-linux-amd64.zip && \
    cd rclone-*-linux-amd64 && \
    cp rclone /usr/bin/ && \
    chmod 755 /usr/bin/rclone


COPY cvmfs_default.local /etc/cvmfs/default.local

# No need to have autofs process running, we mount manually

ENTRYPOINT for DIR in $CVMFS_REPOSITORIES; do mkdir -p /cvmfs/$DIR && mount -t cvmfs $DIR /cvmfs/$DIR; done && \
	sleep infinity
