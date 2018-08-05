cmake_minimum_required(VERSION 2.8.12)

project(
    noise-c
    LANGUAGES C
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

enable_testing()
add_subdirectory(tests)

include(CTest)
