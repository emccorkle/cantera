cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources testWaterPDSS.cpp)
set(resources output_blessed.txt)

# Setup executable
add_executable(cathermo_testWaterPDSS ${sources} ${resources})
target_link_libraries(cathermo_testWaterPDSS cantera)


