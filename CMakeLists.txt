cmake_minimum_required(VERSION 3.14)
project(MyCpp20Project)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Find GTest
find_package(GTest REQUIRED)

# Source files
file(GLOB_RECURSE SOURCES "src/*.cpp")
add_executable(${PROJECT_NAME} ${SOURCES})

# Test files
file(GLOB_RECURSE TEST_SOURCES "test/*.cpp")
add_executable(tests ${TEST_SOURCES})
target_link_libraries(tests GTest::gtest_main)

# Enable testing
enable_testing()
add_test(NAME AllTests COMMAND tests)
