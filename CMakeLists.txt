cmake_minimum_required(VERSION 3.15)
project(ace LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(src)

if(BUILD_TESTING)
  enable_testing()
  find_package(GTest REQUIRED)
  add_subdirectory(test)
endif()
