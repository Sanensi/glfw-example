﻿# CMakeList.txt : CMake project for glfw-example, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

# Enable Hot Reload for MSVC compilers if supported.
if (POLICY CMP0141)
  cmake_policy(SET CMP0141 NEW)
  set(CMAKE_MSVC_DEBUG_INFORMATION_FORMAT "$<IF:$<AND:$<C_COMPILER_ID:MSVC>,$<CXX_COMPILER_ID:MSVC>>,$<$<CONFIG:Debug,RelWithDebInfo>:EditAndContinue>,$<$<CONFIG:Debug,RelWithDebInfo>:ProgramDatabase>>")
endif()

project ("glfw-example")

# Add source to this project's executable.
include_directories("deps")
add_subdirectory("deps/glfw")

add_executable (glfw-example "glfw-example.c"  "deps/glad/gl.h" "deps/linmath.h")
target_link_libraries(glfw-example glfw)


if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET glfw-example PROPERTY CXX_STANDARD 20)
endif()

# TODO: Add tests and install targets if needed.
