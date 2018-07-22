add_library(noiseprotobufs STATIC protobufs.c)

target_include_directories(noiseprotobufs PUBLIC "${CMAKE_SOURCE_DIR}/include")
