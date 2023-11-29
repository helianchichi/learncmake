cmake_minimum_required(VERSION 3.0)
project(CALC)
set(CMAKE_CXX_STANDARD 17)
include_directories(${PROJECT_SOURCE_DIR}/include)
file(GLOB SRC_LIST ${CMAKE_CURRENT_SOURCE_DIR}/src/*.c)

message("SRC_LIST: ${SRC_LIST}")   # 打印
# add_executable(app  ${SRC_LIST})
set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/lib)
# add_library(calc STATIC ${SRC_LIST})
add_library(calc SHARED ${SRC_LIST})