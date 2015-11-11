FROM ${DOCKER_ORG_NAME}/${PKG_NAME}-deb-init

MAINTAINER "Jiao Lin <jiao.lin@gmail.com>"

RUN curl -s https://packagecloud.io/install/repositories/${PKGCLOUD_USERNAME}/${PKGCLOUD_REPO}/script.deb.sh | bash
RUN apt-get install ${DOCKER_PKGING_DEPS_DEB}
