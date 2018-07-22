add_library(noisekeys STATIC
        certificate.c
        loader.c
)

target_include_directories(noisekeys PRIVATE
        ${CMAKE_SOURCE_DIR}/include
        ${CMAKE_SOURCE_DIR}/include/noise/keys
)

# TODO: whats that protos target
