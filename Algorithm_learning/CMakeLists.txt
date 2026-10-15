cmake_minimum_required(VERSION 3.10)
project(AlgorithmLearning C)

set(CMAKE_C_STANDARD 11)

# 接收外部通过命令行传递进来的源文件名称
if(NOT TARGET_FILE)
    message(FATAL_ERROR "请指定 TARGET_FILE")
endif()

# 自动提取没有后缀的文件名作为可执行程序名（例如 test1.c -> test1）
get_filename_component(EXEC_NAME ${TARGET_FILE} NAME_WE)

# 添加可执行目标
add_executable(${EXEC_NAME} ${TARGET_FILE})