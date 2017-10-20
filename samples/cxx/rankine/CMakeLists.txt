cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources rankine.cpp)
set(resources output_0_blessed.txt)

# Setup executable
add_executable(rankine ${sources} ${resources})
target_link_libraries(rankine cantera)
