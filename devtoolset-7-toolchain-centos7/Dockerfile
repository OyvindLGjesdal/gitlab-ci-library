FROM centos/devtoolset-7-toolchain-centos7:7
USER 0
RUN yum install -y --setopt=tsflags=nodocs git liblcms2-devel libtiff-devel libpng-devel libz-devel && yum clean all -y
USER 1001
