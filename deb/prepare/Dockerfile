FROM ${DOCKER_ORG_NAME}/${PKG_NAME}-deb-init:${DOCKER_PKGING_DEB_DIST_NAME}-${DOCKER_PKGING_DEB_DIST_VERSION}

MAINTAINER "Jiao Lin <jiao.lin@gmail.com>"

RUN curl -s https://packagecloud.io/install/repositories/${PKGCLOUD_USERNAME}/${PKGCLOUD_REPO}/script.deb.sh | bash
RUN apt-get install -y ${DOCKER_PKGING_DEPS_DEB}
