add_executable(echo-client
    echo-client.c
)

target_include_directories(echo-client PRIVATE
    ${CMAKE_SOURCE_DIR}/examples/echo/echo-server
)

target_link_libraries(echo-client noiseprotocol)
