cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources combustor.cpp)
set(resources combustor_blessed_0.csv
              output_0_blessed.txt)

# Setup executable
add_executable(combustor ${sources} ${resources})
target_link_libraries(combustor cantera)
