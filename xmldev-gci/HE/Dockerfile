FROM redhat/ubi9-minimal
ENV XSPEC_VERSION=3.1.2
ENV SAXON_VERSION=12.5
ENV SAXON_HOME=/opt/saxon
ENV ANT_VERSION=1.10.12
ENV ANT_HOME=/opt/ant
ENV PATH="${PATH}:${ANT_HOME}/bin"
ENV JAVA_HOME="/usr/lib/jvm/jre-11/"
ENV XSPEC_HOME=/opt/xspec


WORKDIR /opt/

RUN mkdir $SAXON_HOME \
&& microdnf install -y unzip java-11-openjdk-headless \
&& curl -L -o ant.zip https://archive.apache.org/dist/ant/binaries/apache-ant-${ANT_VERSION}-bin.zip \
&& unzip ant.zip && mv apache-ant-${ANT_VERSION} $ANT_HOME \
&& rm ant.zip \
&& curl -L -o xspec.zip https://github.com/xspec/xspec/archive/refs/tags/v${XSPEC_VERSION}.zip \
&& unzip xspec.zip \
&& mv xspec-${XSPEC_VERSION} $XSPEC_HOME \
&& rm xspec.zip \
&& cd $SAXON_HOME \
&& curl -L -o saxon.zip https://github.com/Saxonica/Saxon-HE/releases/download/SaxonHE12-5/SaxonHE12-5J.zip \
&& unzip saxon.zip && rm saxon.zip \
&& mv saxon-he-${SAXON_VERSION}.jar saxon-he.jar \
&& microdnf remove -y unzip \
&& microdnf clean all \ 
&& rm -r $XSPEC_HOME/test $XSPEC_HOME/tutorial $SAXON_HOME/doc $ANT_HOME/manual

WORKDIR $SAXON_HOME
USER 10001

RUN ls /opt/saxon && ls /opt/ && cd /opt/ && du -h --max-depth 2
