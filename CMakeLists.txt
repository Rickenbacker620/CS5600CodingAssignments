cmake_minimum_required(VERSION 3.10)
project(zombie C)

# Set the C standard
set(CMAKE_C_STANDARD 11)
set(CMAKE_C_STANDARD_REQUIRED ON)

add_subdirectory(haiku)
add_subdirectory(zombie)