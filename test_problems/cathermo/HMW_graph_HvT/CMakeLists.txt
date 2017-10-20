cmake_minimum_required(VERSION 3.5.0)

# Setup executable
add_executable(cathermo_L_standalone L_standalone.cpp)
target_link_libraries(cathermo_L_standalone cantera)

# Collect sources
set(sources HMW_graph_HvT.cpp)
set(resources HMW_NaCl_sp1977_alt.xml
              NaCl_Solid.xml
              output_blessed.txt
              README)

# Setup executable
add_executable(cathermo_HMW_graph_HvT ${sources} ${resources})
target_link_libraries(cathermo_HMW_graph_HvT cantera)
target_include_directories(cathermo_HMW_graph_HvT PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/../../shared)
