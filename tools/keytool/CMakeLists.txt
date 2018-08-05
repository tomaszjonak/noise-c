add_executable(noise-keytool
    generate.c
    keytool.c
    show.c
    sign.c
)

target_link_libraries(noise-keytool PRIVATE
    noisekeys
    noiseprotobufs
    noiseprotocol
)
