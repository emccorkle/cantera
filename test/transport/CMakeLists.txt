cmake_minimum_required(VERSION 3.5.0)

# Setup executable
add_executable(transportTests transportFromScratch.cpp)
target_link_libraries(transportTests cantera)

# Other dependencies
target_link_libraries(transportTests gtest)
target_link_libraries(transportTests gmock)
target_link_libraries(transportTests ${CMAKE_THREAD_LIBS_INT})

# Let cmake know about the tests
add_test(NAME transport COMMAND $<TARGET_FILE:transportTests>)
