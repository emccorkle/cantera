cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources clib_test.c)
set(resources output_blessed.txt)

# Setup executable
add_executable(clib_test ${sources} ${resources})
target_link_libraries(clib_test cantera)
