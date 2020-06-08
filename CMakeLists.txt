cmake_minimum_required(VERSION 3.17)	

project(OpenGLPend)

add_executable(OpenGLPend OpenGLPend.cpp)

set(SOURCE OpenGLPend.cpp PendCalc.cpp stdafx.cpp)

set(HEADER OpenGLPend.h PendCalc.h stdafx.h)

find_package(OpenGL REQUIRED)
if(NOT OPENGL_FOUND)
  message(SEND_ERROR "Failed to find OpenGL")
  return()
endif()

target_link_libraries(OpenGLPend PUBLIC OpenGL::GLU OpenGL::GL)
