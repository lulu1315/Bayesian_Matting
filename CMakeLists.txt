project(bayesianmatting)

cmake_minimum_required(VERSION 2.9)
#add_compile_options(-std=c++11)

find_package(OpenCV 3.2 REQUIRED)

find_package(OpenMP)
if (OPENMP_FOUND)
    set (CMAKE_C_FLAGS "${CMAKE_C_FLAGS} ${OpenMP_C_FLAGS}")
    set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${OpenMP_CXX_FLAGS}")
    set (CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} ${OpenMP_EXE_LINKER_FLAGS}")
endif()

add_executable(bayesianmatting main.cpp bayesian.cpp Cluster.cpp getopt.c)

target_link_libraries(bayesianmatting ${OpenCV_LIBS})
