project(SIMDB_StandaloneThread_test)

add_executable(SIMDB_StandaloneThread_test1 StandaloneThread_test1.cpp)

include(../../TestingMacros.cmake)

simdb_test(SIMDB_StandaloneThread_test1 SIMDB_StandaloneThread_test1_RUN)
