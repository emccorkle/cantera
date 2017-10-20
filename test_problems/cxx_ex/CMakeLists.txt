cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources examples.cpp
            example_utils.h
            equil_example1.cpp
            transport_example1.cpp
            transport_example2.cpp
            kinetics_example1.cpp
            kinetics_example3.cpp
            rxnpath_example1.cpp)
set(resources eq1_blessed.csv
              kin1_blessed.csv
              output_blessed.txt
              silane.xml
              tr1_blessed.csv
              tr2_blessed.csv)

# Setup executable
add_executable(cxx_ex ${sources} ${resources})
target_link_libraries(cxx_ex cantera)
