cmake_minimum_required(VERSION 3.16)

#find_package(GTest REQUIRED)
#include_directories(${GTEST_INCLUDE_DIRS})

include_directories(include)


add_executable(mytest src/test.cpp)

target_link_libraries(mytest matrix)


#
enable_testing()


target_link_libraries(mytest ${GTEST_LIBRARIES} -lpthread)
target_link_libraries(mytest matrix)

include(ExternalProject)
ExternalProject_Add(gtest
  URL https://googletest.googlecode.com/files/gtest-1.7.0.zip
  # Comment above line, and uncomment line below to use subversion.
  # SVN_REPOSITORY http://googletest.googlecode.com/svn/trunk/ 
  # Uncomment line below to freeze a revision (here the one for 1.7.0)
  # SVN_REVISION -r700

  PREFIX ${CMAKE_CURRENT_BINARY_DIR}/gtest
  INSTALL_COMMAND ""
)
ExternalProject_Get_Property(gtest source_dir binary_dir)