add_executable(vector-gen
    vector-gen.c
    simple-cipherstate.c
    simple-handshakestate.c
    simple-symmetricstate.c
)

target_link_libraries(vector-gen PRIVATE noiseprotocol)

target_include_directories(vector-gen PRIVATE
    ${CMAKE_SOURCE_DIR}/src/protocol
)
