cmake_minimum_required(VERSION 3.5)
project(teensy_x86_bounce2_stubs C CXX)
set(teensy_x86_bounce2_stubs_VERSION 1.0.0)

set(CMAKE_CXX_STANDARD 11)

find_library(teensy_x86_stubs NAME teensy_x86_stubs)
include_directories(${teensy_x86_stubs_INCLUDE_DIR})

set(SOURCE_FILES
		Bounce2.cpp)

set(HEADER_FILES
		Bounce2.h)

add_definitions(-DARDUINO=146)
add_library(teensy_x86_bounce2_stubs SHARED STATIC ${HEADER_FILES} ${SOURCE_FILES})

set_target_properties(teensy_x86_bounce2_stubs PROPERTIES PUBLIC_HEADER "${HEADER_FILES}")
