FROM oyvindlg/gitlab-ci-library:xmldev
ENV JENA_VERSION=3.14.0
ENV JENA_HOME=/opt/jena
WORKDIR /opt
RUN yum install -y  unzip && \
rm $SAXON_HOME/$SAXON_FILENAME && \
curl -o jena.zip https://apache.uib.no/jena/binaries/apache-jena-${JENA_VERSION}.zip && \
unzip jena.zip && \
yum clean -y all && \
rm jena.zip
