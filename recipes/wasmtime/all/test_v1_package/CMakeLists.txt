cmake_minimum_required(VERSION 3.8)

project(test_package C)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup(TARGETS)

find_package(wasmtime REQUIRED CONFIG)

add_executable(${PROJECT_NAME} ../test_package/test_package.c)
target_link_libraries(${PROJECT_NAME} PRIVATE wasmtime::wasmtime)
target_compile_features(${PROJECT_NAME} PRIVATE c_std_11)
