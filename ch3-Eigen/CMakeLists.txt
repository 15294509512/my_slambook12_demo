cmake_minimum_required(VERSION 2.8)
project(useEigen)


# 添加Eigen头文件
include_directories( "include" "/usr/include/eigen3")

# 添加libeigenMatrix库
add_library(libeigenMatrix src/libeigenMatrix.cpp)
# 添加libeigenGeometry库
add_library(libeigenGeometry src/libeigenGeometry.cpp)

# 添加一个可执行程序
# 语法：add_executable( 程序名 源代码文件 ）
# 添加可执行程序调用hello库中函数
# 将库文件链接到可执行程序上
add_executable(printf main.cpp)
target_link_libraries(printf libeigenMatrix libeigenGeometry)