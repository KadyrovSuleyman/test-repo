cmake_minimum_required(VERSION 3.16)

include_directories(include)


add_executable(mytest src/test.cpp)
target_link_libraries(mytest matrix)


enable_testing()

target_link_libraries(mytest matrix)

include_directories(gtest)
target_link_libraries(mytest gtest -lpthread)