cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources DH_graph_1.cpp)
set(resources DH_NaCl_acommon.xml
              DH_NaCl_acommon_blessed.csv
              DH_NaCl_bdotak.xml
              DH_NaCl_bdotak_blessed.csv
              DH_NaCl_dilute.xml
              DH_NaCl_dilute_blessed.csv
              DH_NaCl_NM.xml
              DH_NaCl_NM_blessed.csv
              DH_NaCl_Pitzer.xml
              DH_NaCl_Pitzer_blessed.csv
              README)

# Setup executable
add_executable(cathermo_DH_graph_1 ${sources} ${resources})
target_link_libraries(cathermo_DH_graph_1 cantera)
target_include_directories(cathermo_DH_graph_1 PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/../../shared)
