cmake_minimum_required(VERSION 2.8.12)
project(LLVM_TRACER CXX)
enable_testing()

set(CMAKE_INSTALL_PREFIX $ENV{TRACER_HOME})
set(SCRIPT_DIR "${CMAKE_CURRENT_SOURCE_DIR}/cmake-scripts")
include("${SCRIPT_DIR}/TracerConfig.cmake")
include("${SCRIPT_DIR}/findAndSetLLVM.cmake")

set(CMAKE_CXX_COMPILER ${CLANGXX})
SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -D_GLIBCXX_USE_CXX11_ABI=0")

add_subdirectory("${CMAKE_CURRENT_SOURCE_DIR}/full-trace")
add_subdirectory("${CMAKE_CURRENT_SOURCE_DIR}/profile-func")
add_subdirectory("${CMAKE_CURRENT_SOURCE_DIR}/ast-pass")
add_subdirectory("${CMAKE_CURRENT_SOURCE_DIR}/example")
