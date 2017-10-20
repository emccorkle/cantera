cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources flamespeed.cpp)
set(resources flamespeed_blessed_0.csv
              output_0_blessed.txt
              phi_input.txt)

# Setup executable
add_executable(flamespeed ${sources} ${resources})
target_link_libraries(flamespeed cantera)
