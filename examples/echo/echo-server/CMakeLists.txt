add_executable(echo-server
    echo-server.c
    echo-common.c
)

target_link_libraries(echo-server noiseprotocol)
