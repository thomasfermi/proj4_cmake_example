cmake_minimum_required(VERSION 3.1)
project(ProjLibraryExample VERSION 1.0)


find_package(PROJ REQUIRED CONFIG)

add_executable(example_main src/main.cpp)

target_link_libraries(example_main 
		      ${CMAKE_DL_LIBS}
		      PROJ::proj
)