enable_testing()
include_directories(${PNG_INCLUDE_DIR})

add_executable(a1-trap-test a1-trap-test.c utils.c utils-prng.c)
target_link_libraries(a1-trap-test pixman-1 ${PNG_LIBRARY})
add_test(a1-trap-test a1-trap-test)
set_tests_properties (a1-trap-test PROPERTIES TIMEOUT 100)

add_executable(affine-test affine-test.c utils.c utils-prng.c)
target_link_libraries(affine-test pixman-1 ${PNG_LIBRARY})
add_test(affine-test affine-test)
set_tests_properties (affine-test PROPERTIES TIMEOUT 100)

add_executable(alpha-loop alpha-loop.c utils.c utils-prng.c)
target_link_libraries(alpha-loop pixman-1 ${PNG_LIBRARY})
add_test(alpha-loop alpha-loop)
set_tests_properties (alpha-loop PROPERTIES TIMEOUT 100)

add_executable(alphamap alphamap.c utils.c utils-prng.c)
target_link_libraries(alphamap pixman-1 ${PNG_LIBRARY})
add_test(alphamap alphamap)
set_tests_properties (alphamap PROPERTIES TIMEOUT 100)

add_executable(blitters-test blitters-test.c utils.c utils-prng.c)
target_link_libraries(blitters-test pixman-1 ${PNG_LIBRARY})
add_test(blitters-test blitters-test)
set_tests_properties (blitters-test PROPERTIES TIMEOUT 100)

add_executable(check-formats check-formats.c utils.c utils-prng.c)
target_link_libraries(check-formats pixman-1 ${PNG_LIBRARY})
add_test(check-formats check-formats)
set_tests_properties (check-formats PROPERTIES TIMEOUT 100)

add_executable(combiner-test combiner-test.c utils.c utils-prng.c)
target_link_libraries(combiner-test pixman-1 ${PNG_LIBRARY})
add_test(combiner-test combiner-test)
set_tests_properties (combiner-test PROPERTIES TIMEOUT 100)

add_executable(composite composite.c utils.c utils-prng.c)
target_link_libraries(composite pixman-1 ${PNG_LIBRARY})
add_test(composite composite)
set_tests_properties (composite PROPERTIES TIMEOUT 100)

add_executable(composite-traps-test composite-traps-test.c utils.c utils-prng.c)
target_link_libraries(composite-traps-test pixman-1 ${PNG_LIBRARY})
add_test(composite-traps-test composite-traps-test)
set_tests_properties (composite-traps-test PROPERTIES TIMEOUT 100)

add_executable(fetch-test fetch-test.c utils.c utils-prng.c)
target_link_libraries(fetch-test pixman-1 ${PNG_LIBRARY})
add_test(fetch-test fetch-test)
set_tests_properties (fetch-test PROPERTIES TIMEOUT 100)

add_executable(glyph-test glyph-test.c utils.c utils-prng.c)
target_link_libraries(glyph-test pixman-1 ${PNG_LIBRARY})
add_test(glyph-test glyph-test)
set_tests_properties (glyph-test PROPERTIES TIMEOUT 100)

add_executable(gradient-crash-test gradient-crash-test.c utils.c utils-prng.c)
target_link_libraries(gradient-crash-test pixman-1 ${PNG_LIBRARY})
add_test(gradient-crash-test gradient-crash-test)
set_tests_properties (gradient-crash-test PROPERTIES TIMEOUT 100)

add_executable(infinite-loop infinite-loop.c utils.c utils-prng.c)
target_link_libraries(infinite-loop pixman-1 ${PNG_LIBRARY})
add_test(infinite-loop infinite-loop)
set_tests_properties (infinite-loop PROPERTIES TIMEOUT 100)

add_executable(lowlevel-blt-bench lowlevel-blt-bench.c utils.c utils-prng.c)
target_link_libraries(lowlevel-blt-bench pixman-1 ${PNG_LIBRARY})
add_test(lowlevel-blt-bench lowlevel-blt-bench)
set_tests_properties (lowlevel-blt-bench PROPERTIES TIMEOUT 100)

add_executable(matrix-test matrix-test.c utils.c utils-prng.c)
target_link_libraries(matrix-test pixman-1 ${PNG_LIBRARY})
add_test(matrix-test matrix-test)
set_tests_properties (matrix-test PROPERTIES TIMEOUT 100)

add_executable(oob-test oob-test.c utils.c utils-prng.c)
target_link_libraries(oob-test pixman-1 ${PNG_LIBRARY})
add_test(oob-test oob-test)
set_tests_properties (oob-test PROPERTIES TIMEOUT 100)

add_executable(pdf-op-test pdf-op-test.c utils.c utils-prng.c)
target_link_libraries(pdf-op-test pixman-1 ${PNG_LIBRARY})
add_test(pdf-op-test pdf-op-test)
set_tests_properties (pdf-op-test PROPERTIES TIMEOUT 100)

add_executable(pixel-test pixel-test.c utils.c utils-prng.c)
target_link_libraries(pixel-test pixman-1 ${PNG_LIBRARY})
add_test(pixel-test pixel-test)
set_tests_properties (pixel-test PROPERTIES TIMEOUT 100)

add_executable(prng-test prng-test.c utils.c utils-prng.c)
target_link_libraries(prng-test pixman-1 ${PNG_LIBRARY})
add_test(prng-test prng-test)
set_tests_properties (prng-test PROPERTIES TIMEOUT 100)

add_executable(radial-perf-test radial-perf-test.c utils.c utils-prng.c)
target_link_libraries(radial-perf-test pixman-1 ${PNG_LIBRARY})
add_test(radial-perf-test radial-perf-test)
set_tests_properties (radial-perf-test PROPERTIES TIMEOUT 100)

add_executable(region-contains-test region-contains-test.c utils.c utils-prng.c)
target_link_libraries(region-contains-test pixman-1 ${PNG_LIBRARY})
add_test(region-contains-test region-contains-test)
set_tests_properties (region-contains-test PROPERTIES TIMEOUT 100)

add_executable(region-test region-test.c utils.c utils-prng.c)
target_link_libraries(region-test pixman-1 ${PNG_LIBRARY})
add_test(region-test region-test)
set_tests_properties (region-test PROPERTIES TIMEOUT 100)

add_executable(region-translate-test region-translate-test.c utils.c utils-prng.c)
target_link_libraries(region-translate-test pixman-1 ${PNG_LIBRARY})
add_test(region-translate-test region-translate-test)
set_tests_properties (region-translate-test PROPERTIES TIMEOUT 100)

add_executable(rotate-test rotate-test.c utils.c utils-prng.c)
target_link_libraries(rotate-test pixman-1 ${PNG_LIBRARY})
add_test(rotate-test rotate-test)
set_tests_properties (rotate-test PROPERTIES TIMEOUT 100)

add_executable(scaling-bench scaling-bench.c utils.c utils-prng.c)
target_link_libraries(scaling-bench pixman-1 ${PNG_LIBRARY})
add_test(scaling-bench scaling-bench)
set_tests_properties (scaling-bench PROPERTIES TIMEOUT 100)

add_executable(scaling-crash-test scaling-crash-test.c utils.c utils-prng.c)
target_link_libraries(scaling-crash-test pixman-1 ${PNG_LIBRARY})
add_test(scaling-crash-test scaling-crash-test)
set_tests_properties (scaling-crash-test PROPERTIES TIMEOUT 100)

add_executable(scaling-helpers-test scaling-helpers-test.c utils.c utils-prng.c)
target_link_libraries(scaling-helpers-test pixman-1 ${PNG_LIBRARY})
add_test(scaling-helpers-test scaling-helpers-test)
set_tests_properties (scaling-helpers-test PROPERTIES TIMEOUT 100)

add_executable(scaling-test scaling-test.c utils.c utils-prng.c)
target_link_libraries(scaling-test pixman-1 ${PNG_LIBRARY})
add_test(scaling-test scaling-test)
set_tests_properties (scaling-test PROPERTIES TIMEOUT 100)

add_executable(stress-test stress-test.c utils.c utils-prng.c)
target_link_libraries(stress-test pixman-1 ${PNG_LIBRARY})
add_test(stress-test stress-test)
set_tests_properties (stress-test PROPERTIES TIMEOUT 100)

add_executable(thread-test thread-test.c utils.c utils-prng.c)
target_link_libraries(thread-test pixman-1 ${PNG_LIBRARY})
add_test(thread-test thread-test)
set_tests_properties (thread-test PROPERTIES TIMEOUT 100)

add_executable(tolerance-test tolerance-test.c utils.c utils-prng.c)
target_link_libraries(tolerance-test pixman-1 ${PNG_LIBRARY})
add_test(tolerance-test tolerance-test)
set_tests_properties (tolerance-test PROPERTIES TIMEOUT 100)

add_executable(trap-crasher trap-crasher.c utils.c utils-prng.c)
target_link_libraries(trap-crasher pixman-1 ${PNG_LIBRARY})
add_test(trap-crasher trap-crasher)
set_tests_properties (trap-crasher PROPERTIES TIMEOUT 100)