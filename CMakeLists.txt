cmake_minimum_required (VERSION 3.0)
project (Intercept-Examples)

set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/CMakeModules)
include(${PROJECT_SOURCE_DIR}/CMakeModules/cxx_compiler_functions.cmake)

option(USE_STATIC_LINKING "USE_STATIC_LINKING" ON)

if(USE_STATIC_LINKING) 
	message("WARNING: Linking statically")
	set(INTERCEPT_LINK_TYPE "static")
else()
	message("WARNING: Linking dynamically")
	set(INTERCEPT_LINK_TYPE "dynamic")
endif()

message("GENERATOR USED: '${CMAKE_GENERATOR}'")

set (CMAKE_RUNTIME_OUTPUT_DIRECTORY "${PROJECT_SOURCE_DIR}/build/win32/")

SET(CMAKE_INCLUDE_CURRENT_DIR ON) 
set_property(GLOBAL PROPERTY USE_FOLDERS ON)

add_subdirectory(src)


