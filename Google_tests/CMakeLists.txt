# Project name
project(Google_tests)

# googletests sources
add_subdirectory(lib)

set(gtest_SOURCE_DIR ./lib/googletest)
include_directories($(gtest_SOURCE_DIR)/include $(gtest_SOURCE_DIR))



# adding the Google_Tests_run target
add_executable(Google_Tests_run ConverterTests.cpp AbsoluteDateTest.cpp)

# linking Google_Tests_run with DateConverter_lib which will be tested
target_link_libraries(Google_Tests_run DateConverter_lib)

target_link_libraries(Google_Tests_run gtest gtest_main)