INCLUDE_DIRECTORIES(include)
ADD_LIBRARY(matrix STATIC src/matrix.c)

ADD_SUBDIRECTORY(tests) 

add_executable(main src/main.c)
target_link_libraries(main matrix)