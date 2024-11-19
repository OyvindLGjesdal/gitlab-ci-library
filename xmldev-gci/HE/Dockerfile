From redhat:ubi9
ENV XPSEC_VERSION v2.2.4
ENV SAXON_VERSION 12.5
ENV SAXON_HOME /opt/saxon
ENV SAXON_FILENAME saxonhe.jar
ENV ANT_VERSION 1.10.12
ENV ANT_HOME /opt/ant
ENV PATH "${PATH}:${ANT_HOME}/bin"
ENV JAVA_HOME "/usr/lib/jvm/jre-11/"



WORKDIR /opt/

RUN mkdir $SAXON_HOME \
&& dnf install -y git \ 
java-11-openjdk-headless \
unzip \
&& curl -o ant.zip https://archive.apache.org/dist/ant/binaries/apache-ant-${ANT_VERSION}-bin.zip \
&& unzip ant.zip && mv apache-ant-${ANT_VERSION} $ANT_HOME \
&& rm ant.zip \
&& git clone https://github.com/xspec/xspec.git \
&& curl -o saxon.zip https://github.com/Saxonica/Saxon-HE/releases/download/SaxonHE12-5/SaxonHE12-5J.zip \
&& unzip saxon.zip \
&& cd /opt/xspec \
&& git checkout ${XSPEC_VERSION}
&& dnf clean -y all

WORKDIR /opt/xspec

WORKDIR $SAXON_HOME
USER 10001

RUN ls /opt/saxon && ls /opt/
