FROM ${DOCKER_ORG_NAME}/${PKG_NAME}-${DOCKER_PKGING_RPM_DIST_NAME}-${DOCKER_PKGING_RPM_DIST_VERSION}-srpm-init

MAINTAINER "Jiao Lin <jiao.lin@gmail.com>"

RUN curl -s https://packagecloud.io/install/repositories/${PKGCLOUD_USERNAME}/${PKGCLOUD_REPO}/script.rpm.sh | bash
RUN yum install -y ${DOCKER_PKGING_DEPS_RPM}
