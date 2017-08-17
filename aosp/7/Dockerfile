FROM ubuntu:16.04

MAINTAINER Tommy Lau <tommy@gen-new.com>

# Install needed packages for building AOSP
RUN sudo dpkg --add-architecture i386 \
	&& apt-get update && apt-get install -y \
		automake \
		bison \
		build-essential \
		bzip2 \
		ccache \
		curl \
		dpkg-dev \
		g++-multilib \
		git \
		gperf \
		libbz2-1.0 \
		libbz2-dev \
		libghc-bzlib-dev \
		liblz4-tool \
		libxml2-utils \
		lzop \
		make \
		maven \
		optipng \
		pngcrush \
		python-networkx \
		schedtool \
		squashfs-tools \
		zip \
		zlib1g-dev \
		zlib1g-dev:i386 \
		--no-install-recommends \
	&& apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Use bash shell instead of dash
RUN echo "dash dash/sh boolean false" | debconf-set-selections && DEBIAN_FRONTEND=noninteractive dpkg-reconfigure dash

# Use UTF-8 as default encoding
ENV LANG C.UTF-8

# Prepare the directory needed for running ssh server
RUN mkdir /var/run/sshd

# SSH Port
EXPOSE 22

# Start SSH server in foreground
CMD ["/usr/sbin/sshd", "-D"]
