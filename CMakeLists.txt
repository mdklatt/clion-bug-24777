cmake_minimum_required(VERSION 3.14)

project(clion-bug
    VERSION 0.1.0.0
    LANGUAGES CXX
)


set(TARGET clion-bug)

add_executable(${TARGET})

target_sources(${TARGET}
PRIVATE
    src/main.cpp
)


target_include_directories(${TARGET}
PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/include
)

target_compile_features(${TARGET}
PRIVATE
    cxx_std_11
)

target_compile_options(${TARGET}
PRIVATE
    -Wall
    -Wno-unknown-pragmas
    $<$<CXX_COMPILER_ID:GNU>:-pedantic>
    --include=version.hpp
)
