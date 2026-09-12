cmake_minimum_required(VERSION 3.19)
project(hyprtoolkit_autopkgtest LANGUAGES CXX)
enable_testing()

set(CMAKE_CXX_STANDARD 23)

find_package(PkgConfig REQUIRED)
find_package(GTest REQUIRED)
pkg_check_modules(HYPRTOOLKIT REQUIRED IMPORTED_TARGET hyprtoolkit)
pkg_check_modules(EGL REQUIRED IMPORTED_TARGET egl)
pkg_check_modules(GLES REQUIRED IMPORTED_TARGET glesv2)

include(GoogleTest)
add_executable(embeddedRendererTest EmbeddedRenderer.cpp)
target_link_libraries(embeddedRendererTest PRIVATE
    PkgConfig::HYPRTOOLKIT PkgConfig::EGL PkgConfig::GLES
    GTest::gtest_main)
gtest_discover_tests(embeddedRendererTest)
