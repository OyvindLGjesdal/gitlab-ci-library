From centos:centos7
ENV XPSEC_VERSION v2.0.7
ENV SAXON_VERSION 10.3
ENV SAXON_HOME /opt/saxon
ENV SAXON_FILENAME saxonhe.jar
ENV ANT_VERSION 1.10.9
ENV ANT_HOME /opt/ant
ENV PATH "${PATH}:${ANT_HOME}/bin"

WORKDIR /opt/

RUN mkdir $SAXON_HOME \
&& yum install -y git \ 
java-11-openjdk \
unzip \
&& curl -o ant.zip https://apache.uib.no/ant/binaries/apache-ant-${ANT_VERSION}-bin.zip \
&& unzip ant.zip && mv apache-ant-${ANT_VERSION} $ANT_HOME \
&& rm ant.zip \
&& git clone https://github.com/xspec/xspec.git \
&& yum clean -y all

WORKDIR /opt/xspec

RUN git checkout ${XSPEC_VERSION}

WORKDIR $SAXON_HOME
RUN curl -o $SAXON_FILENAME https://repo1.maven.org/maven2/net/sf/saxon/Saxon-HE/${SAXON_VERSION}/Saxon-HE-${SAXON_VERSION}.jar
