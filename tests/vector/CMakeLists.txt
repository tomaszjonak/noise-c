add_executable(test-vector
    test-vector.c
    json-reader.c
)

target_link_libraries(test-vector noiseprotocol)

add_test(vector-tests test-vector
    "${CMAKE_CURRENT_SOURCE_DIR}/cacophony.txt"
    "${CMAKE_CURRENT_SOURCE_DIR}/noise-c-basic.txt"
    "${CMAKE_CURRENT_SOURCE_DIR}/noise-c-fallback.txt"
    "${CMAKE_CURRENT_SOURCE_DIR}/noise-c-hybrid.txt"
)
