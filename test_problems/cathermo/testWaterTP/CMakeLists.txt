cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources testWaterSSTP.cpp)
set(resources output_blessed.txt
              README
              waterTPphase.xml)

# Setup executable
add_executable(cathermo_testWaterTP ${sources} ${resources})
target_link_libraries(cathermo_testWaterTP cantera)


