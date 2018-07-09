cmake_minimum_required(VERSION 3.10)
project(lz4 C)

add_library(lz4_static STATIC
    lib/lz4.c
    lib/lz4.h
    lib/lz4frame.c
    lib/lz4frame_static.h
    lib/lz4frame.h
    lib/lz4hc.c
    lib/lz4hc.h
    lib/xxhash.c
    lib/xxhash.h
    )
target_include_directories(lz4_static
    PUBLIC
    lib
    )

add_executable(simpleBuffer
    examples/simple_buffer.c)
target_link_libraries(simpleBuffer
    PUBLIC
    lz4_static)
