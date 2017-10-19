cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources kineticsFromScratch.cpp
            pdep.cpp
            rates.cpp)

# Setup executable
add_executable(kineticsTests ${sources})
target_link_libraries(kineticsTests cantera)

# Other dependencies
target_link_libraries(kineticsTests gtest)
target_link_libraries(kineticsTests gmock)
target_link_libraries(kineticsTests ${CMAKE_THREAD_LIBS_INT})

# Let cmake know about the tests
add_test(NAME kinetics COMMAND $<TARGET_FILE:kineticsTests>)
