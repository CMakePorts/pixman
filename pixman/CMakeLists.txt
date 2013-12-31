configure_file(pixman-version.h.in ${CMAKE_CURRENT_BINARY_DIR}/pixman-version.h)

set(SOURCES
    pixman.c
    pixman-access.c
    pixman-access-accessors.c
    pixman-bits-image.c
    pixman-combine32.c
    pixman-combine-float.c
    pixman-conical-gradient.c
    pixman-filter.c
    pixman-x86.c
    pixman-mips.c
    pixman-arm.c
    pixman-ppc.c
    pixman-edge.c
    pixman-edge-accessors.c
    pixman-fast-path.c
    pixman-glyph.c
    pixman-general.c
    pixman-gradient-walker.c
    pixman-image.c
    pixman-implementation.c
    pixman-linear-gradient.c
    pixman-matrix.c
    pixman-noop.c
    pixman-radial-gradient.c
    pixman-region16.c
    pixman-region32.c
    pixman-solid-fill.c
    pixman-timer.c
    pixman-trap.c
    pixman-utils.c
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

# MMX compilation flags
if(MMX_VAR)
    set(MMX_CFLAGS -DUSE_X86_MMX -w14710 -w14714)
    add_definitions(${MMX_CFLAGS})
    list(APPEND SOURCES pixman-mmx.c)
endif()

# SSE2 compilation flags
if(SSE2_VAR)
    set(SSE2_CFLAGS -DUSE_SSE2)
    add_definitions(${SSE2_CFLAGS})
    list(APPEND SOURCES pixman-sse2.c)
endif()

# SSSE3 compilation flags
if(SSSE3_VAR)
    set(SSSE3_CFLAGS -DUSE_SSSE3)
    add_definitions(${SSE2_CFLAGS})
    list(APPEND SOURCES pixman-ssse3.c.c)
endif()

IF(CMAKE_COMPILER_IS_GNUCXX AND NOT WIN32)
	set(CMAKE_C_FLAGS -fPIC)
ENDIF(CMAKE_COMPILER_IS_GNUCXX AND NOT WIN32) 

add_library(pixman-1 STATIC ${SOURCES} ${HEADERS})
target_link_libraries(pixman-1)

install(TARGETS pixman-1 RUNTIME DESTINATION bin ARCHIVE DESTINATION lib)
install(FILES pixman.h ${CMAKE_CURRENT_BINARY_DIR}/pixman-version.h DESTINATION include/pixman-1)
