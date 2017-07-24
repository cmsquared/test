cmake_minimum_required(VERSION 3.0)

project(mytest)

include_directories(${CMAKE_CURRENT_SOURCE_DIR})
add_subdirectory(src)

add_subdirectory(apps)

## Docs
find_package(Doxygen REQUIRED)
set(_directory ${CMAKE_BINARY_DIR}/doc/${PROJECT_NAME})
set(${PROJECT_NAME}_DOXYGEN_TARGET ${PROJECT_NAME}/doxygen)
if(NOT EXISTS ${_directory})
  file(MAKE_DIRECTORY ${_directory})
endif()
if(NOT EXISTS ${_directory}/.doxygen)
  file(MAKE_DIRECTORY ${_directory}/.doxygen)
endif()
configure_file(${CMAKE_CURRENT_SOURCE_DIR}/doc/doxygen.conf.in
  ${_directory}/.doxygen/doxygen.conf)
add_custom_target(doxygen
  ${DOXYGEN} ${_directory}/.doxygen/doxygen.conf
  DEPENDS ${CMAKE_CURRENT_SOURCE_DIR}/doc/doxygen.conf.in)
