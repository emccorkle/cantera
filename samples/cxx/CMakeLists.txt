cmake_minimum_required(VERSION 3.5.0)

# Add demo sample
add_executable(demo demo.cpp)
target_link_libraries(demo cantera)

# Add individual samples
add_subdirectory(bvp)
add_subdirectory(combustor)
add_subdirectory(flamespeed)
add_subdirectory(kinetics1)
add_subdirectory(LiC6_electrode)
add_subdirectory(NASA_coeffs)
add_subdirectory(openmp_ignition)
add_subdirectory(rankine)
