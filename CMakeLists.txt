cmake_minimum_required(VERSION 3.14)

project(CMakeTest VERSION 1.0)

find_package(glfw3 3.3 REQUIRED)

add_subdirectory(glad)

add_executable(main main.cpp shader.h)

add_custom_command(TARGET main PRE_BUILD 
	COMMAND ${CMAKE_COMMAND} -E copy_directory
	${CMAKE_SOURCE_DIR}/shaders/ $<TARGET_FILE_DIR:main>/shaders/)

target_link_libraries(main PUBLIC glfw glad)

target_include_directories(main PUBLIC  "${PROJECT_SOURCE_DIR}/glad/include")
