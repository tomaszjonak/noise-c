add_executable(test-noise
    test-cipherstate.c
    test-dhstate.c
    test-errors.c
    test-handshakestate.c
    test-hashstate.c
    test-main.c
    test-names.c
    test-patterns.c
    test-protobufs.c
    test-randstate.c
    test-signstate.c
    test-symmetricstate.c
)

target_include_directories(test-noise PRIVATE
    ${CMAKE_SOURCE_DIR}/src
)

target_link_libraries(test-noise PRIVATE
    noisekeys
    noiseprotobufs
    noiseprotocol
)

add_test(unit-tests test-noise)
