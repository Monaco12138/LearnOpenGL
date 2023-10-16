cmake_minimum_required (VERSION 3.0)
cmake_policy(VERSION 3.0)

project(LearnOpenGL)

find_package(OpenGL REQUIRED)

add_library(glad glad.c)
target_include_directories(glad PUBLIC "/home/netlab/main/LearnOpenGL/includes")

set (CMAKE_CXX_LINK_EXECUTABLE "${CMAKE_CXX_LINK_EXECUTABLE} -ldl")

add_executable(hello_test hello_test.cpp)

target_link_libraries(hello_test glfw ${GL_LIBRARY} glad)