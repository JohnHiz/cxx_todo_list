cmake_minimum_required(VERSION 3.10)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(todo_list
    DESCRIPTION To-Do List using C++ and command line.
    VERSION 0.0.1
    LANGUAGES CXX)

add_subdirectory(src)
