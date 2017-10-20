cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources HMW_graph_GvI.cpp)
set(resources HMW_NaCl.xml
              README
              T298_blessed.csv
              T523_blessed.csv)

# Setup executable
add_executable(cathermo_HMW_graph_GvI ${sources} ${resources})
target_link_libraries(cathermo_HMW_graph_GvI cantera)


