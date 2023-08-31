cmake_minimum_required(VERSION 3.26)
set(CMAKE_EXPERIMENTAL_CXX_MODULE_CMAKE_API "2182bf5c-ef0d-489a-91da-49dbc3090d2a")

# MSVC module flag
set(CMAKE_EXPERIMENTAL_CXX_MODULE_DYNDEP 1)

project(modules_test)

set(CMAKE_CXX_STANDARD 23)
add_executable(modules_test main.cpp)

add_library(modules)

target_sources(modules
    PUBLIC
    FILE_SET cxx_modules TYPE CXX_MODULES FILES
    test_module.ixx
)


target_link_libraries(modules_test PRIVATE modules)
