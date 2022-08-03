cmake_minimum_required(VERSION 3.14...3.23)

project(
  intermediate-c-2nd-edition-basic
  VERSION 0.1
  DESCRIPTION "Basic CMake Template for Intermediate C Programming"
  LANGUAGES C CXX
)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

set(CMAKE_CXX_STANDARD 17)

include(FetchContent)

FetchContent_Declare(
  googletest
  GIT_REPOSITORY https://github.com/google/googletest.git
  GIT_TAG        release-1.11.0
)

# cmake Windows issue: Prevent overriding the parent project's compiler/linker settings
set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)

FetchContent_MakeAvailable(googletest)

add_subdirectory(hello-exe)
add_subdirectory(hello-lib)
