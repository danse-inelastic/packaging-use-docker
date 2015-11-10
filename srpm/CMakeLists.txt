# docker 

configure_file(prepare/Dockerfile prepare/Dockerfile)
configure_file(prepare/run.in prepare/run)

configure_file(build/Dockerfile.in build/Dockerfile)
configure_file(build/run.in build/run)
configure_file(build/upload.in build/upload)

configure_file(test/Dockerfile.in test/Dockerfile)
configure_file(test/run.in test/run)
configure_file(test/upload.in test/upload)

add_custom_target( 
  build-srpm-deps
  COMMAND bash run
  WORKING_DIRECTORY prepare
  )

# output under ..../build/SRPMS/
add_custom_target( 
  build-srpm
  COMMAND bash run
  WORKING_DIRECTORY build
  )
add_dependencies(build-srpm build-srpm-deps)

add_custom_target( 
  upload-srpm
  COMMAND bash upload
  WORKING_DIRECTORY build
  )
add_dependencies(upload-srpm build-srpm)

add_custom_target( 
  test-srpm
  COMMAND bash run
  WORKING_DIRECTORY test
  )
add_dependencies(test-srpm upload-srpm)

add_custom_target( 
  upload-rpms
  COMMAND bash upload
  WORKING_DIRECTORY test
  )
add_dependencies(upload-rpms test-srpm)