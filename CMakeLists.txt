cmake_minimum_required(VERSION 2.8)

include(ExternalProject)

ExternalProject_Add(
    example_A
    URL
    https://github.com/forexample/example-A/archive/v1.0.1.tar.gz
    CMAKE_ARGS
    -DCMAKE_VERBOSE_MAKEFILE=ON
    -DCMAKE_INSTALL_PREFIX=${CMAKE_CURRENT_LIST_DIR}/Install
    TEST_BEFORE_INSTALL
    1
)

ExternalProject_Add(
    example_B
    DEPENDS
    example_A
    URL
    https://github.com/forexample/example-B/archive/v1.0.1.tar.gz
    CMAKE_ARGS
    -DCMAKE_VERBOSE_MAKEFILE=ON
    -DCMAKE_INSTALL_PREFIX=${CMAKE_CURRENT_LIST_DIR}/Install
    TEST_BEFORE_INSTALL
    1
)
