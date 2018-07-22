cmake_minimum_required(VERSION 2.6)
project(noise-c C)



#if (${})
#    set(ED448_DEFAULT_ARCH arch_x86_64)
#else()
if ("${CMAKE_SIZEOF_VOID_P}" STREQUAL "8")
    set(ED448_DEFAULT_ARCH arch_ref64)
else()
    set(ED448_DEFAULT_ARCH arch_32)
endif ()
#endif ()

set(GOLDILOCKS_ARCH "${ED448_DEFAULT_ARCH}")

add_subdirectory(include)
add_subdirectory(src)
add_subdirectory(examples)
#add_subdirectory(tests)
