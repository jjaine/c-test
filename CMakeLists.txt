cmake_minimum_required(VERSION 3.14)
project(c-test)

# Executable from main.c called main
add_executable(main src/main.c src/source.c)

# Setup tests

# GoogleTest requires at least C++14
set(CMAKE_CXX_STANDARD 14)

include(FetchContent)
FetchContent_Declare(
  googletest
  URL https://github.com/google/googletest/archive/609281088cfefc76f9d0ce82e1ff6c30cc3591e5.zip
)
FetchContent_MakeAvailable(googletest)

enable_testing()

add_executable(sample_test
  test/test.cc
  src/source.c
)

target_link_libraries(
  sample_test
  gtest_main
)

include(GoogleTest)
gtest_discover_tests(sample_test)

