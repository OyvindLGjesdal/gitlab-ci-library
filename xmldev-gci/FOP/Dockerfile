FROM oyvindlg/gitlab-ci-library:xmldev
ENV FOP_VERSION 2.8
ENV FOP_HOME /opt/fop
RUN mkdir $FOP_HOME && \
cd $FOP_HOME && \
curl -o fop.tar.gz https://archive.apache.org/dist/xmlgraphics/fop/binaries/fop-${FOP_VERSION}-bin.tar.gz && \
tar --extract --file=fop.tar.gz --strip-components=2 fop-${FOP_VERSION}/fop && \
 rm fop.tar.gz && \
ls -alh
COPY build.xml ${FOP_HOME}/build.xml
