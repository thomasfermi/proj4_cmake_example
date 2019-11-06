cmake_minimum_required(VERSION 3.1)
project(ProjLibraryExample VERSION 1.0)

SET(CMAKE_CXX_COMPILER /usr/bin/clang++)

find_package(PROJ4 CONFIG REQUIRED)

add_executable(example_main src/main.cpp)

target_link_libraries(example_main 
		      ${CMAKE_DL_LIBS}
		      proj 
		      PROJ4::proj  

)

