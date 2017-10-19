cmake_minimum_required(VERSION 3.5.0)

# Setup executable
add_executable(equilTests equil_gas.cpp)
target_link_libraries(equilTests cantera)

# Other dependencies
target_link_libraries(equilTests gtest)
target_link_libraries(equilTests gmock)
target_link_libraries(equilTests ${CMAKE_THREAD_LIBS_INT})

# Let cmake know about the tests
add_test(NAME equil COMMAND $<TARGET_FILE:equilTests>)
