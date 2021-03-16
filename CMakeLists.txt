cmake_minimum_required(VERSION 3.16)
project(matrix)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_FLAGS "${CMAKE_C_FLAGS} -std=c++0x -Wall -Werror -Wextra -ggdb3 -fprofile-arcs -ftest-coverage -fPIC")

add_subdirectory(project)

enable_testing()

include_directories(googletest)
target_link_libraries(mytest gtest -lpthread)

add_subdirectory(googletest)


set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/CMakeModules)
if(CMAKE_COMPILER_IS_GNUCXX)
    include(CodeCoverage)
    append_coverage_compiler_flags()

    # setup_target_for_coverage(${PROJECT_NAME}_coverage ${PROJECT_TEST_NAME} coverage)

    # setup_target_for_coverage(${PROJECT_NAME}_coverage ${PROJECT_TEST_NAME} coverage)

# set(COVERAGE_EXCLUDES
#           dir1
#           dir2)

set(COVERAGE_LCOV_EXCLUDES 'dir1/*' 'dir2/*')
# SETUP_TARGET_FOR_COVERAGE_LCOV(NAME matrix_coverage
#                               EXECUTABLE matrix
#                               DEPENDENCIES matrix)

endif()

# if(CMAKE_COMPILER_IS_GNUCXX)
#     target_link_libraries(${PROJECT_TEST_NAME} gcov)
# endif()

# option(ENABLE_COVERAGE "Build all tests." ON) # Makes boolean 'test' available.
# if(ENABLE_COVERAGE)
#     set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g ")
#     set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O0")
#     set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fprofile-arcs")
#     set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -ftest-coverage")
#     set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} --coverage")
# endif()





