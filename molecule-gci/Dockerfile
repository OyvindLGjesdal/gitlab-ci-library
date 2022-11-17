From docker:stable-dind

RUN apk update && \
apk add --no-cache   python3 python3-dev py3-pip \
gcc git curl build-base \
autoconf automake py3-cryptography linux-headers \
musl-dev libffi-dev openssl-dev openssl openssh ca-certificates && \
update-ca-certificates --fresh && \
docker info && \
python3 -m pip install ansible molecule[docker]
