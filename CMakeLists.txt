
set(DOCKER_ORG_NAME "danseins")

# by default, use master branch
if ("${GITHUB_BRANCH}" STREQUAL "")
  set(GITHUB_BRANCH "master")
endif()

# by default, use build command is "make"
if ("${DOCKER_PKGING_BUILDSTEP_BUILDCMD}" STREQUAL "")
  set(DOCKER_PKGING_BUILDSTEP_BUILDCMD "make")
endif()

add_subdirectory(srpm)
add_subdirectory(deb)
