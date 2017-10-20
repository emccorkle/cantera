cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources nacl_equil.cpp)
set(resources gas.xml
              good_out.txt
              HMW_NaCl.xml
              NaCl_Solid.xml
              README
              vcs_equilibrate_blessed.csv)

# Setup executable
add_executable(VCSnonideal_NaCl_equil ${sources} ${resources})
target_link_libraries(VCSnonideal_NaCl_equil cantera)
