cmake_minimum_required(VERSION 3.5.0)

# Project/metadata
project(cantera VERSION 2.4.0)

# Project-wise compiler and linker settings
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
if(NOT DEFINED CMAKE_SUPPRESS_DEVELOPER_WARNINGS)
    set(CMAKE_SUPPRESS_DEVELOPER_WARNINGS ON CACHE INTERNAL "No dev warnings")
endif()
if(MSVC)
    add_compile_options(/W3)
    add_definitions(/D_CRT_SECURE_NO_WARNINGS /D_SCL_SECURE_NO_WARNINGS)
else()
    add_compile_options(-fPIC -Wall -Wpedantic -Werror)
endif()

# Common build/install settings
set(GENERATED_DIR ${CMAKE_CURRENT_BINARY_DIR}/generated)
set(CONFIG_INSTALL_DIR cmake/${PROJECT_NAME})
set(NAMESPACE ${PROJECT_NAME}::)

# Options
# add_definitions(/DCT_USE_LAPACK)

# Find Threads
find_package(Threads REQUIRED)

# Find GoogleTest
set(gtest_force_shared_crt ON CACHE BOOL "Always use shared C runtime" )
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/ext/googletest)

# Find fmt
set(FMT_DOC OFF)
set(FMT_INSTALL OFF)
set(FMT_TEST OFF)
set(BUILD_SHARED_LIBS OFF)
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/ext/fmt)

# Find libexecstream
add_library(libexecstream STATIC ${CMAKE_CURRENT_SOURCE_DIR}/ext/libexecstream/exec-stream.cpp)

# Find sundials
set(BUILD_SHARED_LIBS OFF)
set(BUILD_STATIC_LIBS ON)
set(EXAMPLES_ENABLE OFF)
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/ext/sundials)

# Find Boost
find_package(Boost 1.65.1 REQUIRED)

# Enable testing
enable_testing()

# Individual targets
add_subdirectory(src)
add_subdirectory(test)
add_subdirectory(samples/cxx)

# Organization
set_property(GLOBAL PROPERTY USE_FOLDERS ON)
set_target_properties(cantera PROPERTIES FOLDER cantera)
#set_target_properties(cantera_shared PROPERTIES FOLDER cantera)
set_target_properties(equilTests PROPERTIES FOLDER test)
set_target_properties(generalTests PROPERTIES FOLDER test)
set_target_properties(kineticsTests PROPERTIES FOLDER test)
set_target_properties(thermoTests PROPERTIES FOLDER test)
set_target_properties(transportTests PROPERTIES FOLDER test)
set_target_properties(demo PROPERTIES FOLDER samples/cxx)
set_target_properties(bvp PROPERTIES FOLDER samples/cxx)
set_target_properties(combustor PROPERTIES FOLDER samples/cxx)
set_target_properties(flamespeed PROPERTIES FOLDER samples/cxx)
set_target_properties(kinetics1 PROPERTIES FOLDER samples/cxx)
set_target_properties(LiC6_electrode PROPERTIES FOLDER samples/cxx)
set_target_properties(NASA_coeffs PROPERTIES FOLDER samples/cxx)
set_target_properties(openmp_ignition PROPERTIES FOLDER samples/cxx)
set_target_properties(rankine PROPERTIES FOLDER samples/cxx)
set_target_properties(gtest PROPERTIES FOLDER ext/googletest/gtest)
set_target_properties(gtest_main PROPERTIES FOLDER ext/googletest/gtest)
set_target_properties(gmock PROPERTIES FOLDER ext/googletest/gmock)
set_target_properties(gmock_main PROPERTIES FOLDER ext/googletest/gmock)
set_target_properties(fmt PROPERTIES FOLDER ext/fmt)
set_target_properties(libexecstream PROPERTIES FOLDER ext/libexecstream)
set_target_properties(sundials_arkode_static PROPERTIES FOLDER ext/sundials)
set_target_properties(sundials_cvode_static PROPERTIES FOLDER ext/sundials)
set_target_properties(sundials_cvodes_static PROPERTIES FOLDER ext/sundials)
set_target_properties(sundials_ida_static PROPERTIES FOLDER ext/sundials)
set_target_properties(sundials_idas_static PROPERTIES FOLDER ext/sundials)
set_target_properties(sundials_kinsol_static PROPERTIES FOLDER ext/sundials)
set_target_properties(sundials_nvecserial_static PROPERTIES FOLDER ext/sundials)


# Export info
include(CMakePackageConfigHelpers)
configure_package_config_file(Config.cmake.in
                              ${GENERATED_DIR}/${PROJECT_NAME}Config.cmake
                              INSTALL_DESTINATION ${CONFIG_INSTALL_DIR})
write_basic_package_version_file(${GENERATED_DIR}/${PROJECT_NAME}ConfigVersion.cmake
                                 COMPATIBILITY ExactVersion)
install(FILES
        ${GENERATED_DIR}/${PROJECT_NAME}Config.cmake
        ${GENERATED_DIR}/${PROJECT_NAME}ConfigVersion.cmake
        DESTINATION ${CONFIG_INSTALL_DIR})
