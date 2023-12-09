cmake_minimum_required(VERSION 3.22)

project(seastar-bootstrap)

find_program(CCACHE_FOUND ccache)
if (CCACHE_FOUND)
    set_property(GLOBAL PROPERTY RULE_LAUNCH_COMPILE ccache)
endif(CCACHE_FOUND)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(Seastar_CXX_DIALECT "gnu++20" CACHE STRING "")
add_subdirectory(contrib/seastar)

add_executable(app main.cc)

target_link_libraries(app PRIVATE Seastar::seastar)
