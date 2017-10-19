cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources MaskellSolidSolnPhase_Test.cpp
            nasapoly.cpp
            phaseConstructors.cpp
            RedlichKisterTest.cpp
            RedlichKwongMFTP_Test.cpp
            thermo_data.h
            thermoParameterizations.cpp
            ThermoPhase_Test.cpp
            water_iapws.cpp)

# Setup executable
add_executable(thermoTests ${sources})
target_link_libraries(thermoTests cantera)

# Other dependencies
target_link_libraries(thermoTests gtest)
target_link_libraries(thermoTests gmock)
target_link_libraries(thermoTests ${CMAKE_THREAD_LIBS_INT})

# Let cmake know about the tests
add_test(NAME thermo COMMAND $<TARGET_FILE:thermoTests>)
