
set(DOCKER_ORG_NAME "danseins")

# by default, use master branch
if ("${GITHUB_BRANCH}" STREQUAL "")
  set(GITHUB_BRANCH "master")
endif()

# by default, use build command is "make"
if ("${DOCKER_PKGING_BUILDSTEP_BUILDCMD}" STREQUAL "")
  set(DOCKER_PKGING_BUILDSTEP_BUILDCMD "make")
endif()

# by default, debian is ubuntu:14.04
if ("${DOCKER_PKGING_DEB_DIST_NAME}" STREQUAL "")
  set(DOCKER_PKGING_DEB_DIST_NAME "ubuntu")
  set(DOCKER_PKGING_DEB_DIST_VERSION "14.04")
endif()

add_subdirectory(srpm)
add_subdirectory(deb)
