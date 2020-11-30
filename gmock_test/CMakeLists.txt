# adding the gmock_Tests_run target
add_executable(gmock_Tests_run FooMain.cpp )

# linking gmock_Tests_run with gtest_lib which will be tested

target_link_libraries(gmock_Tests_run gtest gtest_main gmock gmock_main )
