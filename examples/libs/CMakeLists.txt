cmake_minimum_required(VERSION 3.20)

project(Libs LANGUAGES C)

set(CMAKE_STATIC_LIBRARY_SUFFIX ".a" CACHE STRING "" FORCE)

add_library(my_awesome_lib)

target_sources(my_awesome_lib PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/src/awesome.c)
target_include_directories(my_awesome_lib PUBLIC ${CMAKE_SOURCE_DIR}/inc)
target_compile_options(my_awesome_lib PUBLIC --no_fragments)

add_subdirectory(lib)

target_link_libraries(my_awesome_lib lib)

target_link_options(my_awesome_lib PRIVATE --semihosting)
