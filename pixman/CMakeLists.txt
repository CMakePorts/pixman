configure_file(pixman-version.h.in ${CMAKE_CURRENT_BINARY_DIR}/pixman-version.h)

set(SOURCES
    pixman.c
    pixman-access.c
    pixman-access-accessors.c
    pixman-arm.c
    pixman-bits-image.c
    pixman-combine32.c
    pixman-combine-float.c
    pixman-conical-gradient.c
    pixman-edge.c
    pixman-edge-accessors.c
    pixman-fast-path.c
    pixman-filter.c
    pixman-general.c
    pixman-glyph.c
    pixman-gradient-walker.c
    pixman-image.c
    pixman-implementation.c
    pixman-linear-gradient.c
    pixman-matrix.c
    pixman-mips.c
    pixman-noop.c
    pixman-ppc.c
    pixman-radial-gradient.c
    pixman-region16.c
    pixman-region32.c
    pixman-solid-fill.c
    pixman-timer.c
    pixman-trap.c
    pixman-utils.c
    pixman-x86.c
)

set(HEADERS
    pixman.h
    pixman-accessor.h
    pixman-combine32.h
    pixman-compiler.h
    pixman-edge-imp.h
    pixman-inlines.h
    pixman-private.h
)

#proccesor_optimizations
if(ARM)
    if (ARM_NEON)
        list(APPEND SOURCES "pixman-arm-neon.c")
    endif (ARM_NEON)
    if (ARM_SIMD)
        list(APPEND SOURCES "pixman-arm-simd.c")
    endif (ARM_SIMD)
endif(ARM)   

if(MIPS)
    if (MIPS_DSPR2)
        list(APPEND SOURCES "pixman-mips-dspr2.c")
    endif (MIPS_DSPR2)
endif(MIPS)  

if(PPC)
    if (PPC_VMX)
        list(APPEND SOURCES "pixman-vmx.c")
    endif (PPC_VMX)
endif(PPC)  

if(X86)
    if (X86_MMX)
        list(APPEND SOURCES "pixman-mmx.c")
    endif (X86_MMX)
    if (X86_SSE2)
        list(APPEND SOURCES "pixman-sse2.c")
    endif (X86_SSE2)
    if (X86_SSSE3)
        list(APPEND SOURCES "pixman-ssse3.c")
    endif(X86_SSSE3)
endif(X86)

IF(CMAKE_COMPILER_IS_GNUCXX AND NOT WIN32)
	set(CMAKE_C_FLAGS -fPIC)
ENDIF(CMAKE_COMPILER_IS_GNUCXX AND NOT WIN32) 

if(BUILD_SHARED)
    add_library(pixman-1 SHARED ${SOURCES} ${HEADERS})
    target_link_libraries(pixman-1)
    install(TARGETS pixman-1 RUNTIME DESTINATION bin ARCHIVE DESTINATION lib)
endif()

if(BUILD_STATIC)
    add_library(pixman-1_static STATIC ${SOURCES} ${HEADERS})
    if(NOT MSVC)
        set_target_properties(pixman-1_static PROPERTIES OUTPUT_NAME pixman-1)
    endif(NOT MSVC)
    target_link_libraries(pixman-1_static)
    install(TARGETS pixman-1_static RUNTIME DESTINATION bin ARCHIVE DESTINATION lib)
endif(BUILD_STATIC)

install(FILES pixman.h ${CMAKE_CURRENT_BINARY_DIR}/pixman-version.h DESTINATION include/pixman-1)