
set(DOCKER_ORG_NAME "danseins")

# by default, use master branch
if ("${GITHUB_BRANCH}" STREQUAL "")
  set(GITHUB_BRANCH "master")
endif()

add_subdirectory(srpm)
add_subdirectory(deb)
