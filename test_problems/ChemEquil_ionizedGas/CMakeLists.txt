cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources ionizedGasEquil.cpp)
set(resources air_below6000K.cti
              output_blessed.txt
              table_blessed.csv)


# Setup executable
add_executable(ChemEquil_ionizedGas ${sources} ${resources})
target_link_libraries(ChemEquil_ionizedGas cantera)
