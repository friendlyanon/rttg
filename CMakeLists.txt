CMAKE_MINIMUM_REQUIRED(VERSION 3.1)

PROJECT(rttg LANGUAGES CXX)
SET(CMAKE_CXX_STANDARD 17)

SET(RTTG_DIR ${CMAKE_SOURCE_DIR}/include/)
MESSAGE("Include directory: ${RTTG_DIR}")

ADD_LIBRARY(rttg INTERFACE)
TARGET_INCLUDE_DIRECTORIES(rttg INTERFACE ${RTTG_DIR})

OPTION(BUILD_EXAMPLES "Build examples" ON)
if (BUILD_EXAMPLES)
    ADD_SUBDIRECTORY("examples/print_tuple_elements")
    ADD_SUBDIRECTORY("examples/modify_tuple_elements")
endif()