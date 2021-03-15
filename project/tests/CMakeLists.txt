cmake_minimum_required(VERSION 3.16)

#find_package(GTest REQUIRED)
#include_directories(${GTEST_INCLUDE_DIRS})

include_directories(include)


add_executable(mytest src/test.cpp)

#add_library(matrix1 STATIC project/src/matrix.c)
#target_link_libraries(mytest matrix1)

target_link_libraries(mytest matrix)


#
enable_testing()


#target_link_libraries(mytest ${GTEST_LIBRARIES} -lpthread)
target_link_libraries(mytest matrix)

include_directories(gtest)
target_link_libraries(mytest gtest -lpthread)