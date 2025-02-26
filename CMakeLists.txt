```cmake
cmake_minimum_required(VERSION 3.10)
project(example)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(src)
add_subdirectory(test)

# Find and link GTest
find_package(GTest REQUIRED)

# Example executable
add_executable(example src/main.cpp) # Replace with your actual source files

# Example test
add_executable(example_test test/test_example.cpp) # Replace with your actual test files
target_link_libraries(example_test GTest::gtest_main) 
```
