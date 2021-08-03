cmake_minimum_required(VERSION 3.14)

project(CMakeTest VERSION 1.0
                  DESCRIPTION "Project to test cmake"
                  LANGUAGES C CXX)

find_package(glfw3 3.3 REQUIRED)

add_subdirectory(glad/)

add_executable(main main.cpp)

target_link_libraries(main glfw glad)