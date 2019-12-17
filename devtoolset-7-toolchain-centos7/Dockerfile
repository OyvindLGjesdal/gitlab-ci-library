FROM centos/devtoolset-7-toolchain-centos7:7
USER 0
RUN yum install -y --setopt=tsflags=nodocs git && yum clean all -y
USER 1001
