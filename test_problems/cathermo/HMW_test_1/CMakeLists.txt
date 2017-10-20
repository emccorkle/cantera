cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources HMW_test_1.cpp)
set(resources HMW_NaCl.xml
              output_noD_blessed.txt
              README)

# Setup executable
add_executable(cathermo_HMW_test_1 ${sources} ${resources})
target_link_libraries(cathermo_HMW_test_1 cantera)


