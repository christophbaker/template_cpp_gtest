include(FetchContent)

FetchContent_Declare(
        googletest
        GIT_REPOSITORY https://github.com/google/googletest.git
        GIT_TAG release-1.11.0
)

#set(gtest_force_shared_crt OFF CACHE BOOL "" FORCE)
# Force Google Test to link the C/C++ runtimes dynamically when
# building on Visual Studio
# Link:
# * https://github.com/google/googletest/tree/release-1.8.1/googletest#visual-studio-dynamic-vs-static-runtimes
if (MSVC)
  set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)
endif()

# Fetch GoogleTest amd make build scripts available
FetchContent_MakeAvailable(googletest)

include(GoogleTest)

set(TEST_NAME GildedRoseUnitTests)

# add_executable(${TEST_NAME} GildedRoseApprovalTests.cc)
# # target_sources(${TEST_NAME} PRIVATE GildedRoseApprovalTests.cc)
# target_link_libraries(${TEST_NAME} src gtest gtest_main)
# gtest_discover_tests(${TEST_NAME})

add_executable(${TEST_NAME} sample_test.cc)
target_link_libraries(${TEST_NAME} PRIVATE src gtest_main)
gtest_discover_tests(${TEST_NAME})
