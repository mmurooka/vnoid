cmake_minimum_required(VERSION 3.1)
project(vnoid)

add_compile_options(-std=c++11)


find_package(PkgConfig)
pkg_check_modules(CNOID REQUIRED choreonoid)
execute_process(COMMAND ${PKG_CONFIG_EXECUTABLE} --variable=sharedir choreonoid
  OUTPUT_VARIABLE CNOID_SHARE_SUBDIR
  OUTPUT_STRIP_TRAILING_WHITESPACE)

install(DIRECTORY model   DESTINATION ${CNOID_SHARE_SUBDIR})
install(DIRECTORY project DESTINATION ${CNOID_SHARE_SUBDIR})

# add_subdirectory(src)
# add_subdirectory(controller)
