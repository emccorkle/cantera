cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources blasius.cpp
            BoundaryValueProblem.h)
set(resources README)

# Setup executable
add_executable(bvp ${sources} ${resources})
target_link_libraries(bvp cantera)
