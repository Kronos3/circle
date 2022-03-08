cmake_minimum_required(VERSION 3.10)
project(circle)
enable_language(C CXX ASM)

add_subdirectory(lib)
add_subdirectory(addon)

target_include_directories(circle PUBLIC
        ${CMAKE_CURRENT_LIST_DIR}/include
        ${CMAKE_CURRENT_LIST_DIR}/addon)
