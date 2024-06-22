cmake_minimum_required(VERSION 3.10)

# Include GoogleTest framework
add_subdirectory(googletest)

# Include the source directory to find headers
include_directories(${CMAKE_SOURCE_DIR}/src)

# Create a library from mylib.cpp
add_library(mylib ${CMAKE_SOURCE_DIR}/src/mylib.cpp)

# Add test source files
add_executable(runTests test_mylib.cpp)

# Link the test executable against GoogleTest libraries and mylib
target_link_libraries(runTests gtest gtest_main mylib)

# Enable testing
include(GoogleTest)
gtest_discover_tests(runTests)

