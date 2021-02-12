From centos:centos7
ENV XPSEC_VERSION v2.0.7
ENV SAXON_VERSION 10.3
ENV SAXON_HOME /opt/saxon
ENV SAXON_FILENAME Saxon9HE.jar
WORKDIR /opt/
RUN mkdir $SAXON_HOME \
&& yum install -y ant \
git \ 
openjdk-1.8 \
&& git clone https://github.com/xspec/xspec.git \
&& cd /opt/xspec \
&& git checkout ${XSPEC_VERSION} \
&& cd $SAXON_HOME \
&& curl -o $SAXON_FILENAME https://repo1.maven.org/maven2/net/sf/saxon/Saxon-HE/${SAXON_VERSION}/Saxon-HE-${SAXON_VERSION}.jar \
&& yum clean -y all
