cmake_minimum_required(VERSION 3.5)
project(teensy_x86_bounce2_stubs C CXX)
set(teensy_x86_bounce2_stubs_VERSION 1.0.0)
set(CMAKE_CXX_STANDARD 11)

cmake_policy(SET CMP0077 NEW)

include(FetchContent)
FetchContent_Declare(cmake_declare_and_fetch
        GIT_REPOSITORY https://github.com/newdigate/cmake-declare-and-fetch.git
        GIT_TAG        main
)
FetchContent_MakeAvailable(cmake_declare_and_fetch)
include("${FETCHCONTENT_BASE_DIR}/cmake_declare_and_fetch-src/DeclareAndFetchCMake.in")

set(BUILD_SHARED_LIBRARY ON)
set(REDIRECT_SERIAL_OUT_TO_STD_OUT OFF)
DeclareAndFetch(teensy_x86_stubs            https://github.com/newdigate/teensy-x86-stubs.git noinstall src)

add_subdirectory(src)