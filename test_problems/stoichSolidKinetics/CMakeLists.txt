cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources stoichSolidKinetics.cpp)
set(resources gas.xml
              output_blessed.txt
              ReactionSurf.xml
              solidPhases.xml)

# Setup executable
add_executable(stoichSolidKinetics ${sources} ${resources})
target_link_libraries(stoichSolidKinetics cantera)
