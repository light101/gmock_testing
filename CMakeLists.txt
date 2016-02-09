cmake_minimum_required(VERSION 2.8)

find_package(Threads)


#add gmock includes
set(GMOCK_DIR ../googlemock)
set(GTEST_DIR ../googletest)
set(GMOCK_HOME /home/light1/Program_World/3rdPartyLibs/googletest)
set(GMOCK_DIR_INC ${GMOCK_DIR}/include)
set(GTEST_DIR_INC ${GTEST_DIR}/include)
set(GMOCK_DIR_LIB ${GMOCK_HOME}/build/googlemock/)
set(GTEST_DIR_LIB ${GMOCK_HOME}/build/googlemock/gtest/)


include_directories(${GMOCK_DIR_INC})
include_directories(${GTEST_DIR_INC})

message(STATUS "GMOCK Dir: " ${GMOCK_DIR})
message(STATUS "GTEST Dir: " ${GTEST_DIR})
message(STATUS "GMOCK Inc: " ${GMOCK_DIR_INC})
message(STATUS "GTEST Inc: " ${GTEST_DIR_INC})
message(STATUS "GMOCK Lib: " ${GMOCK_DIR_LIB})


add_executable(SoundExTest SoundexTest.cc)

#link_directories(${GMOCK_DIR_LIB})
target_link_libraries(SoundExTest ${GMOCK_DIR_LIB}libgmock.a ${GMOCK_DIR_LIB}libgmock_main.a ${GTEST_DIR_LIB}libgtest.a ${GTEST_DIR_LIB}libgtest_main.a ${CMAKE_THREAD_LIBS_INIT})

