cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources rankine.cpp)
set(resources output_blessed.txt)

# Setup executable
add_executable(rankine_democxx ${sources} ${resources})
target_link_libraries(rankine_democxx cantera)
