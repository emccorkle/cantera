cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources LiC6_electrode.cpp)
set(resources LiC6_electrodebulk.xml
              potentials_blessed.dat)

# Setup executable
add_executable(LiC6_electrode ${sources} ${resources})
target_link_libraries(LiC6_electrode cantera)
