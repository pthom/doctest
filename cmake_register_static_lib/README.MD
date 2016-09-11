# Quick usage Instruction

`doctest_registerlibrary.cmake` enables you to add doctest to a static library easily.

Minimal example below :
````
# cmake 3.0 minimum is required
cmake_minimum_required(VERSION 3.0)

# You need to set doctest_lib_location to where you
# installed doctest.
# This can be done once in a common cmake file
set(doctest_lib_location WhereYouInstalledDoctest)
include(${doctest_lib_location}/cmake_register_static_lib/register_static_lib.cmake)

# Every time you add a library that you want to add tests to
add_library(YourLibraryName STATIC somefiles.cpp)

# Just call doctest_register_static_lib with
# - the name of the library
# - the name of the test executable that will be generated
doctest_register_static_lib(YourLibraryName YourLibraryName_Test)
````
