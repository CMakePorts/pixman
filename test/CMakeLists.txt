include_directories(${PNG_INCLUDE_DIR})

add_executable(a1-trap-test a1-trap-test.c utils.c utils-prng.c)
target_link_libraries(a1-trap-test pixman-1 ${PNG_LIBRARY})

add_executable(affine-test affine-test.c utils.c utils-prng.c)
target_link_libraries(affine-test pixman-1 ${PNG_LIBRARY})

add_executable(alpha-loop alpha-loop.c utils.c utils-prng.c)
target_link_libraries(alpha-loop pixman-1 ${PNG_LIBRARY})

add_executable(alphamap alphamap.c utils.c utils-prng.c)
target_link_libraries(alphamap pixman-1 ${PNG_LIBRARY})

add_executable(blitters-test blitters-test.c utils.c utils-prng.c)
target_link_libraries(blitters-test pixman-1 ${PNG_LIBRARY})

add_executable(check-formats check-formats.c utils.c utils-prng.c)
target_link_libraries(check-formats pixman-1 ${PNG_LIBRARY})

add_executable(combiner-test combiner-test.c utils.c utils-prng.c)
target_link_libraries(combiner-test pixman-1 ${PNG_LIBRARY})

add_executable(composite composite.c utils.c utils-prng.c)
target_link_libraries(composite pixman-1 ${PNG_LIBRARY})

add_executable(composite-traps-test composite-traps-test.c utils.c utils-prng.c)
target_link_libraries(composite-traps-test pixman-1 ${PNG_LIBRARY})

add_executable(fetch-test fetch-test.c utils.c utils-prng.c)
target_link_libraries(fetch-test pixman-1 ${PNG_LIBRARY})

add_executable(glyph-test glyph-test.c utils.c utils-prng.c)
target_link_libraries(glyph-test pixman-1 ${PNG_LIBRARY})

add_executable(gradient-crash-test gradient-crash-test.c utils.c utils-prng.c)
target_link_libraries(gradient-crash-test pixman-1 ${PNG_LIBRARY})

add_executable(infinite-loop infinite-loop.c utils.c utils-prng.c)
target_link_libraries(infinite-loop pixman-1 ${PNG_LIBRARY})

add_executable(lowlevel-blt-bench lowlevel-blt-bench.c utils.c utils-prng.c)
target_link_libraries(lowlevel-blt-bench pixman-1 ${PNG_LIBRARY})

add_executable(matrix-test matrix-test.c utils.c utils-prng.c)
target_link_libraries(matrix-test pixman-1 ${PNG_LIBRARY})

add_executable(oob-test oob-test.c utils.c utils-prng.c)
target_link_libraries(oob-test pixman-1 ${PNG_LIBRARY})

add_executable(pdf-op-test pdf-op-test.c utils.c utils-prng.c)
target_link_libraries(pdf-op-test pixman-1 ${PNG_LIBRARY})

add_executable(pixel-test pixel-test.c utils.c utils-prng.c)
target_link_libraries(pixel-test pixman-1 ${PNG_LIBRARY})

add_executable(prng-test prng-test.c utils.c utils-prng.c)
target_link_libraries(prng-test pixman-1 ${PNG_LIBRARY})

add_executable(radial-perf-test radial-perf-test.c utils.c utils-prng.c)
target_link_libraries(radial-perf-test pixman-1 ${PNG_LIBRARY})

add_executable(region-contains-test region-contains-test.c utils.c utils-prng.c)
target_link_libraries(region-contains-test pixman-1 ${PNG_LIBRARY})

add_executable(region-test region-test.c utils.c utils-prng.c)
target_link_libraries(region-test pixman-1 ${PNG_LIBRARY})

add_executable(region-translate-test region-translate-test.c utils.c utils-prng.c)
target_link_libraries(region-translate-test pixman-1 ${PNG_LIBRARY})

add_executable(rotate-test rotate-test.c utils.c utils-prng.c)
target_link_libraries(rotate-test pixman-1 ${PNG_LIBRARY})

add_executable(scaling-bench scaling-bench.c utils.c utils-prng.c)
target_link_libraries(scaling-bench pixman-1 ${PNG_LIBRARY})

add_executable(scaling-crash-test scaling-crash-test.c utils.c utils-prng.c)
target_link_libraries(scaling-crash-test pixman-1 ${PNG_LIBRARY})

add_executable(scaling-helpers-test scaling-helpers-test.c utils.c utils-prng.c)
target_link_libraries(scaling-helpers-test pixman-1 ${PNG_LIBRARY})

add_executable(scaling-test scaling-test.c utils.c utils-prng.c)
target_link_libraries(scaling-test pixman-1 ${PNG_LIBRARY})

add_executable(stress-test stress-test.c utils.c utils-prng.c)
target_link_libraries(stress-test pixman-1 ${PNG_LIBRARY})

add_executable(thread-test thread-test.c utils.c utils-prng.c)
target_link_libraries(thread-test pixman-1 ${PNG_LIBRARY})

add_executable(tolerance-test tolerance-test.c utils.c utils-prng.c)
target_link_libraries(tolerance-test pixman-1 ${PNG_LIBRARY})

add_executable(trap-crasher trap-crasher.c utils.c utils-prng.c)
target_link_libraries(trap-crasher pixman-1 ${PNG_LIBRARY})