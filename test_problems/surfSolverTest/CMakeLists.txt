cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources surfaceSolver.cpp)
set(resources results_blessed.txt
              surfaceSolver_blessed.out)

# Setup executable
add_executable(surfSolverTest1 ${sources} ${resources})
target_link_libraries(surfSolverTest1 cantera)


# Collect sources
set(sources surfaceSolver2.cpp)
set(resources haca2.cti
              results2_blessed.txt
              surfaceSolver2_blessed.out)

# Setup executable
add_executable(surfSolverTest2 ${sources} ${resources})
target_link_libraries(surfSolverTest2 cantera)
