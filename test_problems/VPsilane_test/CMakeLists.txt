cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources silane_equil.cpp)
set(resources silane.xml
              output_blessed.txt)

# Setup executable
add_executable(VPsilane_test ${sources} ${resources})
target_link_libraries(VPsilane_test cantera)
