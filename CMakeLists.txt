project(pixman)

cmake_minimum_required(VERSION 2.8)

#########################################################################
# detect version
#########################################################################
file (READ configure.ac configure_ac)
string (REGEX REPLACE ".*pixman_major], ([0-9]+).*" "\\1" PIXMAN_VERSION_MAJOR ${configure_ac})
string (REGEX REPLACE ".*pixman_minor], ([0-9]+).*" "\\1" PIXMAN_VERSION_MINOR ${configure_ac})
string (REGEX REPLACE ".*pixman_micro], ([0-9]+).*" "\\1" PIXMAN_VERSION_MICRO ${configure_ac})

add_definitions(-DHAVE_CONFIG_H)

configure_file(config.h.cmake ${CMAKE_BINARY_DIR}/config.h)

include_directories(
	${CMAKE_BINARY_DIR}
	${CMAKE_BINARY_DIR}/pixman
	${CMAKE_SOURCE_DIR}/pixman
)

set(pkgconfig_DATA pixman-1.pc)

add_subdirectory(pixman)