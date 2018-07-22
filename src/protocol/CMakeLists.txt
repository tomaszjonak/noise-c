add_library(noiseprotocol STATIC
    cipherstate.c
    dhstate.c
    errors.c
    handshakestate.c
    internal.c
    names.c
    patterns.c
    randstate.c
    signstate.c
    symmetricstate.c
    util.c
    ${CMAKE_SOURCE_DIR}/src/backend/ref/dh-curve448.c
    ${CMAKE_SOURCE_DIR}/src/backend/ref/dh-newhope.c
    ${CMAKE_SOURCE_DIR}/src/backend/ref/hash-blake2s.c
    ${CMAKE_SOURCE_DIR}/src/crypto/blake2/blake2s.c
    ${CMAKE_SOURCE_DIR}/src/crypto/curve448/curve448.c
    ${CMAKE_SOURCE_DIR}/src/crypto/goldilocks/src/p448/${GOLDILOCKS_ARCH}/p448.c
    ${CMAKE_SOURCE_DIR}/src/crypto/newhope/batcher.c
    ${CMAKE_SOURCE_DIR}/src/crypto/newhope/error_correction.c
    ${CMAKE_SOURCE_DIR}/src/crypto/newhope/error_correction.h
    ${CMAKE_SOURCE_DIR}/src/crypto/newhope/fips202.c
    ${CMAKE_SOURCE_DIR}/src/crypto/newhope/fips202.h
    ${CMAKE_SOURCE_DIR}/src/crypto/newhope/newhope.c
    ${CMAKE_SOURCE_DIR}/src/crypto/newhope/newhope.h
    ${CMAKE_SOURCE_DIR}/src/crypto/newhope/ntt.c
    ${CMAKE_SOURCE_DIR}/src/crypto/newhope/ntt.h
    ${CMAKE_SOURCE_DIR}/src/crypto/newhope/params.h
    ${CMAKE_SOURCE_DIR}/src/crypto/newhope/poly.c
    ${CMAKE_SOURCE_DIR}/src/crypto/newhope/poly.h
    ${CMAKE_SOURCE_DIR}/src/crypto/newhope/precomp.c
    ${CMAKE_SOURCE_DIR}/src/crypto/newhope/randombytes.h
    ${CMAKE_SOURCE_DIR}/src/crypto/newhope/reduce.c
    ${CMAKE_SOURCE_DIR}/src/crypto/newhope/reduce
#        If not sodium nor openssl
    ${CMAKE_SOURCE_DIR}/src/backend/ref/cipher-aesgcm.c
#        second part
    rand_os.c
    ${CMAKE_SOURCE_DIR}/src/backend/ref/cipher-aesgcm.c
    ${CMAKE_SOURCE_DIR}/src/backend/ref/cipher-chachapoly.c
    ${CMAKE_SOURCE_DIR}/src/backend/ref/dh-curve25519.c
    ${CMAKE_SOURCE_DIR}/src/backend/ref/hash-blake2b.c
    ${CMAKE_SOURCE_DIR}/src/backend/ref/hash-sha256.c
    ${CMAKE_SOURCE_DIR}/src/backend/ref/hash-sha512.c
    ${CMAKE_SOURCE_DIR}/src/backend/ref/sign-ed25519.c
    ${CMAKE_SOURCE_DIR}/src/crypto/aes/rijndael-alg-fst.c
    ${CMAKE_SOURCE_DIR}/src/crypto/blake2/blake2b.c
    ${CMAKE_SOURCE_DIR}/src/crypto/chacha/chacha.c
    ${CMAKE_SOURCE_DIR}/src/crypto/donna/poly1305-donna.c
    ${CMAKE_SOURCE_DIR}/src/crypto/ghash/ghash.c
    ${CMAKE_SOURCE_DIR}/src/crypto/newhope/crypto_stream_chacha20.c
    ${CMAKE_SOURCE_DIR}/src/crypto/newhope/crypto_stream_chacha20.h
    ${CMAKE_SOURCE_DIR}/src/crypto/sha2/sha256.c
    ${CMAKE_SOURCE_DIR}/src/crypto/sha2/sha512.c
    ${CMAKE_SOURCE_DIR}/src/crypto/ed25519/ed25519.c
)

target_include_directories(noiseprotocol PRIVATE
    ${CMAKE_SOURCE_DIR}/include
    ${CMAKE_SOURCE_DIR}/src
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_SOURCE_DIR}/src/crypto/goldilocks/src/include
    ${CMAKE_SOURCE_DIR}/src/crypto/goldilocks/src/p448
    ${CMAKE_SOURCE_DIR}/src/crypto/goldilocks/src/p448/${GOLDILOCKS_ARCH}
)

target_compile_definitions(noiseprotocol PRIVATE
    ED25519_CUSTOMHASH
    ED25519_CUSTOMRANDOM
)
