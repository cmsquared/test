cmake_minimum_required(VERSION 3.0)

project(mytest)

include_directories(${CMAKE_CURRENT_SOURCE_DIR})
add_subdirectory(src)

add_subdirectory(apps)
