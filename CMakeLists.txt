cmake_minimum_required(VERSION 3.14)
project(example)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(src)
add_subdirectory(test)

find_package(GTest REQUIRED)

add_executable(example src/main.cpp) # Example executable

include_directories(src)


enable_testing()

add_executable(example_tests test/test_example.cpp)
target_link_libraries(example_tests GTest::gtest_main)
target_include_directories(example_tests PRIVATE src)

add_test(NAME example_tests COMMAND example_tests)

