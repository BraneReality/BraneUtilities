cmake_minimum_required(VERSION 3.23)

project(BraneUtilities
        VERSION "0.2.0"
        DESCRIPTION "BraneScript"
        HOMEPAGE_URL "https://github.com/BraneReality/branescript"
        LANGUAGES CXX)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_subdirectory(src)

add_library(utilities INTERFACE)
target_include_directories(utilities INTERFACE ${CMAKE_CURRENT_SRC_DIR}/src)

if(BUILD_TESTS)
    enable_testing()
    add_subdirectory(tests)
endif()
