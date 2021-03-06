# docker 

configure_file(init/Dockerfile init/Dockerfile)
configure_file(init/run.in init/run)

configure_file(prepare/Dockerfile prepare/Dockerfile)
configure_file(prepare/run.in prepare/run)

configure_file(build/Dockerfile.in build/Dockerfile)
configure_file(build/run.in build/run)
configure_file(build/upload.in build/upload)

configure_file(test/Dockerfile.in test/Dockerfile)
configure_file(test/run.in test/run)

add_custom_target( 
  build-deb-init
  COMMAND bash run
  WORKING_DIRECTORY init
  )

add_custom_target( 
  build-deb-deps
  COMMAND bash run
  WORKING_DIRECTORY prepare
  )
add_dependencies(build-deb-deps build-deb-init)

# output under ..../build/DEB
add_custom_target( 
  build-deb
  COMMAND bash run
  WORKING_DIRECTORY build
  )
add_dependencies(build-deb build-deb-deps)

add_custom_target(
  upload-deb
  COMMAND python upload
  WORKING_DIRECTORY build
  )
add_dependencies(upload-deb build-deb)

add_custom_target( 
  test-deb
  COMMAND bash run
  WORKING_DIRECTORY test
  )
add_dependencies(test-deb upload-deb)
