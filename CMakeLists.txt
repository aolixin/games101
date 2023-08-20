# CMakeList.txt: VS2019Cmake 的 CMake 项目，在此处包括源代码并定义
# 项目特定的逻辑。
#
cmake_minimum_required (VERSION 3.8)

project(RayTracing)

set(CMAKE_CXX_STANDARD 17)

# 头文件
include_directories(F:/document/visualPlugin/opencv/build/include)
#include_directories(F:/document/visualPlugin/eigen-3.4.0)

#静态链接库
link_directories(F:/document/visualPlugin/opencv/build/x64/vc15/lib)
# 将 OpenCV 库链接到可执行文件

# 将源代码添加到此项目的可执行文件。
add_executable(RayTracing main.cpp Object.hpp Vector.hpp Sphere.hpp global.hpp Triangle.hpp Scene.cpp Scene.hpp Light.hpp Renderer.cpp)
target_link_libraries(RayTracing ${OpenCV_LIBS} opencv_world3415d.lib)
# TODO: 如有需要，请添加测试并安装目标。




#target_compile_options(RayTracing PUBLIC -Wall -Wextra -pedantic -Wshadow -Wreturn-type -fsanitize=undefined)
target_compile_features(RayTracing PUBLIC cxx_std_17)
#target_link_libraries(RayTracing PUBLIC -fsanitize=undefined)