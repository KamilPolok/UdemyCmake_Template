# 0. Create code and CMake File
# 1. Configure cmake Project
#       1.0. mkdir build
#       1.1. cmake -S <root_directory_path> -B <build_directory_path>
# 2. Build cmake Project
#       2.0. Build whole or part of a project - single target
#            target - single library or executable
#       2.1. cmake --build <build_directory_path>
# 3. Run executable - <build_directory_path>/<executable_name>
cmake_minimum_required(VERSION 3.16)

project(CppProjectTemplate VERSION 1.0.0 LANGUAGES C CXX)

add_library(Library STATIC my_lib.cpp)

add_executable(Executable main.cpp)

target_link_libraries(Executable PUBLIC Library)


