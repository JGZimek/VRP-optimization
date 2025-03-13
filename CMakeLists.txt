cmake_minimum_required(VERSION 3.10)
project(VRP_ACO_Project VERSION 1.0 LANGUAGES CXX)

# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Optionally, set build type to Release by default
if(NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Release)
endif()

# Include directories for headers in the src folder
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/src)

# Gather all source files for the main executable
set(SOURCES
    src/main.cpp
    src/aco/ACO.cpp
    src/aco/Ant.cpp
    src/vrp/VRP.cpp
    src/utils/Utils.cpp
)

# Create the main executable
add_executable(VRP_ACO ${SOURCES})

# (Optional) Link any libraries if needed
# target_link_libraries(VRP_ACO <libraries>)

# Add tests directory if it exists
if(EXISTS "${CMAKE_CURRENT_SOURCE_DIR}/tests")
    enable_testing()
    add_subdirectory(tests)
endif()
