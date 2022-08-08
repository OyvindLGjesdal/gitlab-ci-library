From rockylinux:8

RUN dnf update -y \
&& dnf install -y epel-release openssl \
&& dnf install -y \
python39 \
python39-pip \
git  \
openssh-clients && \
pip3 install "ansible-lint>=5.4,<6.0" "ansible>=2.9,<2.10"
