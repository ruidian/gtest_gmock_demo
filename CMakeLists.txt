cmake_minimum_required(VERSION 3.14)
project(testing_test)

set(CMAKE_CXX_FLAGS_RELEASE "/MT")
set(CMAKE_CXX_FLAGS_DEBUG "/MTd")

set(CMAKE_CXX_STANDARD 14)

set(SOURCE_FILES main.cpp)
add_executable(DateConverter_run ${SOURCE_FILES})

add_subdirectory(Google_tests/lib)
include_directories(${gtest_SOURCE_DIR}/include ${gtest_SOURCE_DIR})
include_directories(${gmock_SOURCE_DIR}/include ${gmock_SOURCE_DIR})

include_directories(DateConverter_lib)
add_subdirectory(DateConverter_lib)
add_subdirectory(Google_tests)
add_subdirectory(gmock_test)

#add_subdirectory(lib)



target_link_libraries(DateConverter_run DateConverter_lib)

