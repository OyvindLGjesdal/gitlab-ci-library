FROM oyvindlg/gitlab-ci-library:xmldev
ENV JENA_VERSION=3.14.0
ENV JENA_HOME=/opt/jena
WORKDIR /opt
RUN yum install -y  unzip && \
curl -o jena.zip https://apache.uib.no/jena/binaries/apache-jena-${JENA_VERSION}.zip && \
unzip jena.zip && \
mv apache-jena-${JENA_VERSION}/ $JENA_HOME && \
rm jena.zip && \
yum remove -y unzip && \
yum clean -y all
