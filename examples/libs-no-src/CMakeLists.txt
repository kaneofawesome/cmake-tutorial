cmake_minimum_required(VERSION 3.20)

project(Libs LANGUAGES C)

add_executable(libs)

target_sources(libs PRIVATE main.c)
include_directories(./lib)
target_link_libraries(libs "${CMAKE_SOURCE_DIR}/lib/my_awesome_lib.a")
target_link_libraries(libs "${CMAKE_SOURCE_DIR}/lib/lib.a")

target_link_options(libs PRIVATE --semihosting)

