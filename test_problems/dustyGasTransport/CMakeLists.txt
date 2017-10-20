cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources dustyGasTransportTest.cpp)
set(resources output_blessed.txt)

# Setup executable
add_executable(dustyGasTransport ${sources} ${resources})
target_link_libraries(dustyGasTransport cantera)
