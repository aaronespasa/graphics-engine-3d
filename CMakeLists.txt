# CMakeLists for OpenGL in MacOS
cmake_minimum_required(VERSION 3.23 FATAL_ERROR)
project(computer-graphics-3d)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# print all warnings
add_compile_options(-Wall -Wextra -Wpedantic)

find_package(glfw3 3.3 REQUIRED)

# add executable
add_executable(main src/main.cpp)
target_include_directories(main PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})

# link libraries
target_link_libraries(main glfw)

find_package(OpenGL REQUIRED)
target_link_libraries(main OpenGL::GL)
