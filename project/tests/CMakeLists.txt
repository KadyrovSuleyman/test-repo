cmake_minimum_required(VERSION 3.16)

#find_package(GTest REQUIRED)
#include_directories(${GTEST_INCLUDE_DIRS})

include_directories(include)


add_executable(mytest src/test.cpp)

target_link_libraries(mytest matrix)


#
enable_testing()


#target_link_libraries(mytest ${GTEST_LIBRARIES} -lpthread)
target_link_libraries(mytest matrix)
