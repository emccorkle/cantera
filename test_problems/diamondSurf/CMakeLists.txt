cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources runDiamond.cpp)
set(resources diamond.cti
              diamond_blessed.xml
              runDiamond_blessed.out)

# Setup executable
add_executable(diamondSurf ${sources} ${resources})
target_link_libraries(diamondSurf cantera)
