cmake_minimum_required(VERSION 3.10)
project(MySampleCppProject)

set(CMAKE_CXX_STANDARD 11)

include_directories(src)

add_executable(MySampleCppProject src/main.cpp src/mylib.cpp)

enable_testing()
add_subdirectory(tests)

