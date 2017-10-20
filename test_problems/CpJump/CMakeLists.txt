cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources CpJump.cpp)
set(resources bad_air.cti
              bad_air.xml
              output_blessed.txt
              README.txt)

# Setup executable
add_executable(CpJump ${sources} ${resources})
target_link_libraries(CpJump cantera)
