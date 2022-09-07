cmake_minimum_required(VERSION 3.1)
project(vnoid)

if(NOT DEFINED OPENHRP3_1_PREFIX)
  find_package(PkgConfig)
  pkg_check_modules(OPENHRP3_1 REQUIRED openhrp3.1)
endif()
message("-- OPENHRP3_1_PREFIX: ${OPENHRP3_1_PREFIX}")

if(NOT DEFINED HRPSYSBASE_PREFIX)
  find_package(PkgConfig)
  pkg_check_modules(HRPSYSBASE REQUIRED hrpsys-base)
endif()
message("-- HRPSYSBASE_PREFIX: ${HRPSYSBASE_PREFIX}")

install(DIRECTORY model DESTINATION ${OPENHRP3_1_PREFIX}/share/OpenHRP-3.1/sample)

configure_file(project/hvac2022_jvrc1.in.cnoid
  ${CMAKE_SOURCE_DIR}/project/hvac2022_jvrc1.cnoid
  @ONLY)

install(FILES project/hvac2022_jvrc1.cnoid DESTINATION ${HRPSYSBASE_PREFIX}/share/hrpsys/samples/JVRC1)
