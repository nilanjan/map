project(Bus_test)

sparta_add_test_executable(Bus_test Bus_main.cpp)

include(../TestingMacros.cmake)

sparta_test(Bus_test Bus_test_RUN)
