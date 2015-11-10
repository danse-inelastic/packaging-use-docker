FROM ubuntu:14.04

MAINTAINER "Jiao Lin <jiao.lin@gmail.com>"

RUN apt-get update
RUN apt-get install -y git build-essential
RUN apt-get install -y cmake
RUN apt-get install -y python python-dev

RUN curl -s https://packagecloud.io/install/repositories/${PKGCLOUD_USERNAME}/${PKGCLOUD_REPO}/script.deb.sh | bash
RUN apt-get install ${DOCKER_PKGING_DEPS_DEB}
