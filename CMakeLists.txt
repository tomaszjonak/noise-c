cmake_minimum_required(VERSION 3.0.0)
cmake_policy(SET CMP0048 NEW)
cmake_policy(SET CMP0057 NEW)

project(
    noise-c
    LANGUAGES C
    VERSION 0.0.1
)

add_compile_options(-Wall)

if ("${CMAKE_SIZEOF_VOID_P}" STREQUAL "8")
    set(ED448_DEFAULT_ARCH arch_ref64)
else()
    set(ED448_DEFAULT_ARCH arch_32)
endif ()

set(GOLDILOCKS_ARCH "${ED448_DEFAULT_ARCH}")

add_subdirectory(include)
add_subdirectory(src)
add_subdirectory(examples)
add_subdirectory(tools)
add_subdirectory(doc)

enable_testing()
add_subdirectory(tests)

include(CTest)
