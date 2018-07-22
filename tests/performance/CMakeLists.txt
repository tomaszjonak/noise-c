add_executable(test-performance
    test-performance.c
    md5.c
)

target_link_libraries(test-performance PRIVATE
    noiseprotocol
)

add_test(performance-tests test-performance)
