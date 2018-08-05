FIND_PACKAGE(Doxygen REQUIRED dot)

if (!${DOXYGEN_FOUND})
    return()
endif()

add_custom_target(doc
    COMMAND doxygen ${CMAKE_CURRENT_SOURCE_DIR}/Doxyfile
    WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
)
