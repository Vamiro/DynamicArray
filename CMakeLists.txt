cmake_minimum_required(VERSION 3.5)

project(DynamicArray VERSION 1.0 LANGUAGES CXX)

if(CMAKE_VERSION VERSION_LESS "3.7.0")
    set(CMAKE_INCLUDE_CURRENT_DIR ON)
endif()

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(googletest)
INCLUDE_DIRECTORIES(${gtest_SOURCE_DIR}/include ${COMMON_INCLUDES})

set(PROJECT_SOURCES
    src/Array.h
    src/QSort.h
    src/unit_tests.cpp
    src/unit_tests.h
)

add_executable(DynamicArray ${PROJECT_SOURCES})

TARGET_LINK_LIBRARIES(DynamicArray gtest)
