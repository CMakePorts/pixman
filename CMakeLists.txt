project(pixman)
set(PACKAGE pixman)

cmake_minimum_required(VERSION 2.8)

# detect version
file (READ configure.ac configure_ac)
string (REGEX REPLACE ".*pixman_major], ([0-9]+).*" "\\1" PIXMAN_VERSION_MAJOR ${configure_ac})
string (REGEX REPLACE ".*pixman_minor], ([0-9]+).*" "\\1" PIXMAN_VERSION_MINOR ${configure_ac})
string (REGEX REPLACE ".*pixman_micro], ([0-9]+).*" "\\1" PIXMAN_VERSION_MICRO ${configure_ac})

#detect target arch
include(${CMAKE_SOURCE_DIR}/cmake/TargetArch.cmake)
target_architecture(ARCHITECTURE)

# architecture set
if(ARCHITECTURE STREQUAL "i386" OR "x86_64") 
    SET(X86 1)
    OPTION(X86_MMX "Enable MMX optimizations" OFF)
    OPTION(X86_SSE2 "Enable SSE2 optimizations" OFF)
    OPTION(X86_SSSE3 "Enable SSSE3 optimizations" OFF)
elseif(ARCHITECTURE STREQUAL "arm")
    SET(ARM 1)
    OPTION(ARM_IWMMXT "Enable IWMMXT compiler intrinsics" OFF)
    OPTION(ARM_NEON "Enable NEON optimizations" OFF)
    OPTION(ARM_SIMD "Enable SIMD optimizations" OFF)
elseif(ARCHITECTURE STREQUAL "ppc" OR "ppc64")
    SET(PPC 1)
    OPTION(PPC_VMX "Enable VMX optimizations" OFF)
else()
    SET(MIPS 1)
    OPTION(MIPS_DSPR2 "Enable DSPR2 optimizations" OFF)
    OPTION(MIPS_LOONGSON_MMI  "Enable Loongson Multimedia Instructions" OFF)
endif(ARCHITECTURE STREQUAL "i386" OR "x86_64")

find_package(PNG)
find_package(Threads)

include(Configure_config.cmake)

include_directories(
	${CMAKE_BINARY_DIR}
	${CMAKE_BINARY_DIR}/pixman
	${CMAKE_SOURCE_DIR}/pixman
)

set(pkgconfig_DATA pixman-1.pc)

add_subdirectory(pixman)
