cmake_minimum_required(VERSION 3.13)

project(jthread)

add_library(jthread INTERFACE)

target_sources(jthread INTERFACE include/jthread.hpp include/stop_token.hpp)

target_include_directories(jthread INTERFACE include/)

