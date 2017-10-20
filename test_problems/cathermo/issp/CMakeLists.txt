cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources ISSPTester.cpp)
set(resources IdealSolidSolnPhaseExample.xml
              output_blessed.txt)

# Setup executable
add_executable(cathermo_issp ${sources} ${resources})
target_link_libraries(cathermo_issp cantera)


