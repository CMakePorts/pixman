project(pixman)
set(PACKAGE pixman)
cmake_minimum_required(VERSION 2.8)

# detect version
file (READ configure.ac configure_ac)
string (REGEX REPLACE ".*pixman_major], ([0-9]+).*" "\\1" PIXMAN_VERSION_MAJOR ${configure_ac})
string (REGEX REPLACE ".*pixman_minor], ([0-9]+).*" "\\1" PIXMAN_VERSION_MINOR ${configure_ac})
string (REGEX REPLACE ".*pixman_micro], ([0-9]+).*" "\\1" PIXMAN_VERSION_MICRO ${configure_ac})

#deps
find_package(PNG)
find_package(Threads)

#arch optimizations
include(${CMAKE_SOURCE_DIR}/cmake/arch_detect.cmake)
include(${CMAKE_SOURCE_DIR}/cmake/arch_configure.cmake)

#config
include(${CMAKE_SOURCE_DIR}/cmake/config_configure.cmake)

option(BUILD_SHARED "build shared library" ON)
option(BUILD_STATIC "build static library" OFF)
option(BUILD_TESTS "build tests" OFF)

include_directories(
	${CMAKE_BINARY_DIR}
	${CMAKE_BINARY_DIR}/pixman
	${CMAKE_SOURCE_DIR}/pixman
)

if(BUILD_SHARED OR BUILD_STATIC)
    add_subdirectory(pixman)
endif()
if(BUILD_TESTS)
    add_subdirectory(test)
endif(BUILD_TESTS)