cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources NASA_coeffs.cpp)
set(resources output_0_blessed.txt)

# Setup executable
add_executable(NASA_coeffs ${sources} ${resources})
target_link_libraries(NASA_coeffs cantera)
