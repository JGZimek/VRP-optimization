# Set up the test executable
file(GLOB TEST_SOURCES *.cpp)

# Create an executable for tests. 
# It is assumed that your test files use a testing framework (e.g., Catch2 or GoogleTest)
add_executable(tests ${TEST_SOURCES})

# Include directories for the tests to access project headers
target_include_directories(tests PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/../src)

# (Optional) Link testing framework libraries if required
# target_link_libraries(tests PRIVATE Catch2::Catch2)

# Register the test with CTest
add_test(NAME AllTests COMMAND tests)
