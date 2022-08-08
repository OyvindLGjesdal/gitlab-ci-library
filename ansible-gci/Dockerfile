From rockylinux:8

RUN dnf update -y \
&& dnf install -y epel-release openssl \
&& dnf install -y ansible \
python39 \
python39-pip \
git  \
openssh-clients && \
pip3 install "ansible-lint[yamllint]"
