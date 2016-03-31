FROM ${DOCKER_FROM_IMG_NAME}:${DOCKER_PKGING_RPM_DIST_VERSION}

MAINTAINER "Jiao Lin <jiao.lin@gmail.com>"

RUN if [ "${DOCKER_FROM_IMG_NAME}" = "centos" ]; then yum -y update && yum clean all && yum -y install epel-release && yum clean all; fi
# RUN yum -y groupinstall "Development tools"

RUN yum install -y deltarpm
RUN yum install -y git cmake make gcc-c++ python python-devel rpm-build
RUN yum install -y curl
