cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources multiGasTransport.cpp)
set(resources output_blessed.txt)

# Setup executable
add_executable(multiGasTransport ${sources} ${resources})
target_link_libraries(multiGasTransport cantera)
