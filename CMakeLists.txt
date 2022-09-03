cmake_minimum_required(VERSION 3.1)
project(vnoid)

find_package(PkgConfig)
pkg_check_modules(OPENHRP3_1 REQUIRED openhrp3.1)
message("- OPENHRP3_1_PREFIX: ${OPENHRP3_1_PREFIX}")

install(DIRECTORY model DESTINATION ${OPENHRP3_1_PREFIX}/share/OpenHRP-3.1/sample)
