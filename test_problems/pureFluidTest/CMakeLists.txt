cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources testPureWater.cpp)
set(resources output_blessed.txt)

# Setup executable
add_executable(pureFluidTest ${sources} ${resources})
target_link_libraries(pureFluidTest cantera)
