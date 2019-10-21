FROM oyvindlg/gitlab-ci-library:xmldev
ENV SAXONPE_VERSION=9-9-1-5
WORKDIR $SAXON_HOME
RUN yum install -y  unzip && \
rm $SAXON_HOME/$SAXON_FILENAME && \
curl -o Saxon9PE.zip https://www.saxonica.com/download/SaxonPE${SAXONPE_VERSION}J.zip && \
unzip Saxon9PE.zip && \
yum clean -y all
