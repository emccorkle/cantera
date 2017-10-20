cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources mixGasTransport.cpp)
set(resources output_blessed.txt)

# Setup executable
add_executable(mixGasTransport ${sources} ${resources})
target_link_libraries(mixGasTransport cantera)
