#PROJECT SETUP
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

#OVERWRITTEN CMAKE VARIABLES
set(CMAKE_CXX_STANDARD 17)              #Every target will be set according to c++17 standard
set(CMAKE_CXX_STANDARD_REQUIRED ON)     #ON/OFF defines if standard from above is required or not
set(CMAKE_CXX_EXTENSIONS OFF)           #ON/OFF defines if c++ extensions, that are not part of c++ standard, are allowed or not

set(LIBRARY_NAME "Library")
set(EXECUTABLE_NAME "Executable")

option(COMPILE_EXECUTABLE "Whether to compile the executable" OFF)

add_subdirectory(src)
if(COMPILE_EXECUTABLE)
    add_subdirectory(app)
else()
    message("Without exe. compiling")
endif()




