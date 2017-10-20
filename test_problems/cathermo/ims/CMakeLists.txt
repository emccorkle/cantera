cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources IMSTester.cpp)
set(resources output_blessed.txt
              WaterPlusSolutes.xml)

# Setup executable
add_executable(cathermo_ims ${sources} ${resources})
target_link_libraries(cathermo_ims cantera)


