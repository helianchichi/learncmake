cmake_minimum_required(VERSION 3.0) # cmake 版本
project(TEST)                       # 项目名字
set(CMAKE_VERBOSE_MAKEFILE ON)      # 编译细节输出  
# set(CMAKE_SKIP_RPATH TRUE)          # 忽略动态库rpath
# add_definitions(-D宏名称)
SET(CMAKE_BUILD_TYPE "Debug")
# SET(CMAKE_BUILD_TYPE "Release")


# message("source path: ${PROJECT_SOURCE_DIR}")   # 打印
file(GLOB SRC_LIST ${CMAKE_CURRENT_SOURCE_DIR}/src/*.c) # 搜索文件，绝对路径
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)    # 头目录
link_directories(${CMAKE_CURRENT_SOURCE_DIR}/lib)           # 库目录

# set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/lib) # 库输出路径
# set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin) # 可执行程序输出路径

# add_library(calc STATIC ${SRC_LIST})  #生成静态库
# add_library(calc SHARED ${SRC_LIST})  #生成动态库
add_executable(app ${SRC_LIST}) # 生成可执行程序

target_link_libraries(app pthread calc) # 链接动态/静态库

# set(tmp1 a;b;c;d;e)   # list tmp1
# set(tmp2 a b c d e)   # list tmp2
# message(${tmp1})    # abcde
# message(${tmp2})    # abcde

# list(APPEND SRC_1 ${SRC_1} ${SRC_2})  # 追加
# list(REMOVE_ITEM SRC_1 ${PROJECT_SOURCE_DIR}/main.cpp)    # 去除
 