cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources string_processing.cpp
            test_containers.cpp
            test_matrices.cpp
            test_numerics.cpp
            test_xml.cpp)

# Setup executable
add_executable(generalTests ${sources})
target_link_libraries(generalTests cantera)

# Other dependencies
target_link_libraries(generalTests gtest)
target_link_libraries(generalTests gmock)
target_link_libraries(generalTests ${CMAKE_THREAD_LIBS_INT})

# Let cmake know about the tests
add_test(NAME general COMMAND $<TARGET_FILE:generalTests>)
