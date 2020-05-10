cmake_minimum_required(VERSION 3.5.1 FATAL_ERROR)

set(CMAKE_CXX_STANDARD 14)
find_package(gazebo REQUIRED)
include_directories(${GAZEBO_INCLUDE_DIRS})
link_directories(${GAZEBO_LIBRARY_DIRS})
list(APPEND CXX_STANDARD_REQUIRED "${GAZEBO_CXX_FLAGS}")

add_library(hello SHARED script/hello.cpp)
target_link_libraries(hello ${GAZEBO_LIBRARIES})