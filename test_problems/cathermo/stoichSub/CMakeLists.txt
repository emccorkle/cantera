cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources stoichSub.cpp)
set(resources NaCl_Solid.xml
              output_blessed.txt)

# Setup executable
add_executable(cathermo_stoichSub ${sources} ${resources})
target_link_libraries(cathermo_stoichSub cantera)
target_include_directories(cathermo_stoichSub PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/../../shared)
