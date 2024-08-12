
# Based on https://github.com/ruven/iipsrv/blob/master/docker/Dockerfile
# IIPImage Dockerfile based on Alpine Linux (stable)
#
# Based on https://github.com/ruven/iipsrv/blob/master/docker/Dockerfile
# with some minor changes for running in our context:
# - doesn't install lighttpd
# - has a dedicated build image and copies to second image
# - runs as a unpriveleged user 
#

# See more on https://github.com/ruven/iipsrv

FROM alpine:latest AS build

MAINTAINER oyvind.gjesdal@uib.no
LABEL url "https://iipimage.sourceforge.io"
LABEL author "Ruven <ruven@users.sourceforge.net>"
EXPOSE 9000

ENV IIPSRV_VERSION=iipsrv-1.2
# Install build dependencies
RUN apk add --no-cache \
	git \
	autoconf \
	automake \
	libtool \
	g++ \
	make \
	fcgi-dev \
	tiff-dev \
	libjpeg-turbo-dev \
	zlib-dev \
	openjpeg-dev \
	libpng-dev \
	libwebp-dev \
	libmemcached-dev

# Get source and checkout version
WORKDIR /usr/local/src/
RUN git clone https://github.com/ruven/iipsrv.git && \
cd iipsrv && \
git checkout $IIPSRV_VERSION
# Checkout correct version
# Configure and compile
WORKDIR /usr/local/src/iipsrv/
RUN ./autogen.sh && \
    ./configure && ls && ls src && pwd

FROM alpine:latest
COPY --from=build /usr/local/src/iipsrv/src/iipsrv.fcgi /usr/local/bin/iipsrv

# Install runtime dependendencies

# Create startup script which starts iipsrv
RUN echo -e "#!/bin/sh\n\
iipsrv --bind \${HOST}:\${PORT}" > /usr/local/bin/run &&\
chmod u+x /usr/local/bin/run
# Create unprivileged user and group 
RUN groupadd -r iipsrv && \
useradd --no-log-init -r -g iipsrv iipsrv
# Set iipsrv environment defaults and execute startup script
ENV HOST="0.0.0.0" PORT="9000" LOGFILE="/dev/stdout" URI_MAP="iiif=>IIIF" VERBOSITY=6 FILESYSTEM_PREFIX="/images/"
USER iipsrv
ENTRYPOINT run
