FIND_PACKAGE(BISON)
FIND_PACKAGE(FLEX)

BISON_TARGET(proto3-parser proto3-grammar.y ${CMAKE_CURRENT_BINARY_DIR}/proto3-grammar.c)
FLEX_TARGET(proto3-scanner proto3-lexer.l  ${CMAKE_CURRENT_BINARY_DIR}/proto3-lexer.c)
ADD_FLEX_BISON_DEPENDENCY(proto3-scanner proto3-parser)

add_executable(noise-protoc
    main.c
    proto3-ast.c
    proto3-generate-c.c
    ${BISON_proto3-parser_OUTPUTS}
    ${FLEX_proto3-scanner_OUTPUTS}
)

target_include_directories(noise-protoc PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
