cmake_minimum_required(VERSION 3.0)
project(mobilenet_demo)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

# include dir
include_directories(${CMAKE_CURRENT_LIST_DIR}/include/)

# libs dir
link_directories(${CMAKE_CURRENT_LIST_DIR}/libs)

# source files
FILE(GLOB SRCS ${CMAKE_CURRENT_LIST_DIR}/mobilenet_demo.cpp)

# target
add_executable(mobilenet_demo ${SRCS})

# link
if (MSVC)
    target_link_libraries(mobilenet_demo MNN)
else()
    target_link_libraries(mobilenet_demo MNN MNN_Express MNNOpenCV)
endif()