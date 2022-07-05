cmake_minimum_required(VERSION 3.13)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(jthread)

add_library(jthread INTERFACE)

target_sources(jthread INTERFACE include/jthread.hpp include/stop_token.hpp)

target_include_directories(jthread INTERFACE include/)

include_directories(include)

enable_testing()

add_executable(test_stoken
        include/stop_token.hpp
        source/condition_variable_any2.hpp
        source/test_stoken.cpp
        source/test.hpp)
add_test(NAME test_stoken COMMAND test_stoken)

add_executable(test_stokencb
        include/stop_token.hpp
        source/condition_variable_any2.hpp
        source/test_stokencb.cpp
        source/test.hpp)
add_test(NAME test_stokencb COMMAND test_stokencb)

add_executable(test_stokenrace
        include/stop_token.hpp
        source/condition_variable_any2.hpp
        source/test_stokenrace.cpp
        source/test.hpp)
add_test(NAME test_stokenrace COMMAND test_stokenrace)

add_executable(test_stopcb
        include/stop_token.hpp
        source/test_stopcb.cpp
        source/test.hpp)
add_test(NAME test_stopcb COMMAND test_stopcb)

add_executable(test_jthread1
        include/stop_token.hpp
        source/condition_variable_any2.hpp
        include/jthread.hpp
        source/test_jthread1.cpp
        source/test.hpp)
add_test(NAME test_jthread1 COMMAND test_jthread1)

add_executable(test_jthread2
        include/stop_token.hpp
        source/condition_variable_any2.hpp
        include/jthread.hpp
        source/test_jthread2.cpp
        source/test.hpp)
add_test(NAME test_jthread2 COMMAND test_jthread2)

add_executable(test_cv
        include/stop_token.hpp
        include/jthread.hpp
        source/condition_variable_any2.hpp
        source/test_cv.cpp
        source/test.hpp)
add_test(NAME test_cv COMMAND test_cv)

add_executable(test_cvcb
        include/stop_token.hpp
        include/jthread.hpp
        source/condition_variable_any2.hpp
        source/test_cvcb.cpp
        source/test.hpp)
add_test(NAME test_cvcb COMMAND test_cvcb)

add_executable(test_cvrace
        include/stop_token.hpp
        include/jthread.hpp
        source/condition_variable_any2.hpp
        source/test_cvrace.cpp
        source/test.hpp)
add_test(NAME test_cvrace COMMAND test_cvrace)

add_executable(test_cvrace_hh
        include/stop_token.hpp
        include/jthread.hpp
        source/condition_variable_any2.hpp
        source/test_cvrace_hh.cpp
        source/test.hpp)
add_test(NAME test_cvrace_hh COMMAND test_cvrace_hh)

add_executable(test_cvrace_stop
        include/stop_token.hpp
        include/jthread.hpp
        source/condition_variable_any2.hpp
        source/test_cvrace_stop.cpp
        source/test.hpp)
add_test(NAME test_cvrace_stop COMMAND test_cvrace_stop)

add_executable(test_cvprodcons
        include/stop_token.hpp
        include/jthread.hpp
        source/condition_variable_any2.hpp
        source/test_cvprodcons.cpp
        source/test.hpp)
add_test(NAME test_cvprodcons COMMAND test_cvprodcons)

add_custom_target(build_tests)
add_dependencies(build_tests
        test_stoken
        test_stokencb
        test_stokenrace
        test_stopcb
        test_jthread1
        test_jthread2
        test_cv
        test_cvcb
        test_cvrace
        test_cvrace_hh
        test_cvrace_stop
        test_cvprodcons)
