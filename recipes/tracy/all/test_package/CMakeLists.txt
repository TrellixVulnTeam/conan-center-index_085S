cmake_minimum_required(VERSION 3.1)
project(test_package)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup(TARGETS)

find_package(tracy REQUIRED)

add_executable(test_package example.cpp)
target_link_libraries(test_package tracy::tracy)
