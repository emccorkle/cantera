cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources wtWater.cpp)
set(resources waterTPphase.xml
              output_blessed.txt)

# Setup executable
add_executable(cathermo_wtWater ${sources} ${resources})
target_link_libraries(cathermo_wtWater cantera)

