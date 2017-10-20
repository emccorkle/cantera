cmake_minimum_required(VERSION 3.5.0)

# Setup executable
add_executable(cathermo_Gex_standalone Gex_standalone.cpp)
target_link_libraries(cathermo_Gex_standalone cantera)

# Collect sources
set(sources HMW_graph_GvT.cpp)
set(resources HMW_NaCl_sp1977_alt.xml
              NaCl_Solid.xml
              output_blessed.txt
              README)

# Setup executable
add_executable(cathermo_HMW_graph_GvT ${sources} ${resources})
target_link_libraries(cathermo_HMW_graph_GvT cantera)
target_include_directories(cathermo_HMW_graph_GvT PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/../../shared)
