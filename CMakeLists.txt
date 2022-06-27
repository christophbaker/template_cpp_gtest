cmake_minimum_required(VERSION 3.22)

set(PROJECT_NAME_STR cpp-gtest-template)
project(${PROJECT_NAME_STR} C CXX)

# GoogleTest requires at least C++11
set(CMAKE_C_STANDARD 99)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_POSITION_INDEPENDENT_CODE ON)

#-------------------
# CMake Modules
#-------------------
# Source: https://github.com/bilke/cmake-modules
# https://stackoverflow.com/questions/13116488/detailed-guide-on-using-gcov-with-cmake-cdash
#list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_LIST_DIR}/modules")

#-------------------
# set common include folder for module
#-------------------
set(COMMON_INCLUDES ${PROJECT_SOURCE_DIR}/include)

# uncomment this line to enable coverage measurements using gcov
#set(CMAKE_CXX_FLAGS "--coverage")

enable_testing()
include_directories(${COMMON_INCLUDES})
add_subdirectory(src)
add_subdirectory(test)
