cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources surfdemo.cpp)
set(resources surface.xml
              output_blessed.txt)

# Setup executable
add_executable(surfkin ${sources} ${resources})
target_link_libraries(surfkin cantera)
