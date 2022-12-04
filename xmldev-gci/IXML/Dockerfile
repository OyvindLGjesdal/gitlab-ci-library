FROM oyvindlg/gitlab-ci-library:xmldev
ENV COFFEEPOT_VERSION=1.99.11
ENV COFFEEPOT_HOME=/opt/coffeepot
WORKDIR /opt
RUN yum install -y  unzip && \
curl -o coffeepot.zip https://github.com/nineml/coffeepot/releases/download/${COFFEEPOT_VERSION}/coffeepot-${COFFEEPOT_VERSION}.zip && \
unzip coffeepot.zip && \
mv coffeepot-${COFFEEPOT_VERSION} $COFFEEPOT_HOME && \
rm coffeepot.zip && \
yum remove -y unzip && \
yum clean -y all
