cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources kinetics1.cpp
            example_utils.h)
set(resources kin1_blessed_0.csv
              output_0_blessed.txt)

# Setup executable
add_executable(kinetics1 ${sources} ${resources})
target_link_libraries(kinetics1 cantera)
