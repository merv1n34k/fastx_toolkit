cmake_minimum_required(VERSION 3.15)
project(fastx_toolkit VERSION 0.0.14
    LANGUAGES C CXX
    )

# Include required CMAKE modules
include(FindPkgConfig)

# Create insterface library for compiler flags
add_library(compiler_flags INTERFACE)

configure_file(config.h.in config.h)

# Specify that any target linking to this library requires C++11 support
target_compile_features(compiler_flags INTERFACE cxx_std_11)

# Options
option(ENABLE_WALL "Enable many common GCC warnings" ON)
option(ENABLE_DEBUG "Enable debug mode" ON)
option(ENABLE_ALL_STATIC "Build completely static (standalone) binaries" OFF)

# Interface Library for Compiler Options
add_library(compiler_options INTERFACE)
add_subdirectory(src)
add_subdirectory(scripts)

# Just for test!
set(ENV{PKG_CONFIG_PATH} "/usr/local/lib/pkgconfig:$ENV{PKG_CONFIG_PATH}")
pkg_search_module(GTEXTUTILS REQUIRED gtextutils)

# Common GCC warnings
if(ENABLE_WALL)
  target_compile_options(compiler_options INTERFACE
    -Wall
    -Wextra
    -Wformat-nonliteral
    -Wformat-security
    -Wswitch-default
    -Wswitch-enum
    -Wunused-parameter
    -Wfloat-equal
    -Werror
  )
endif()

# Debug mode
if(ENABLE_DEBUG)
  target_compile_definitions(compiler_options INTERFACE DEBUG=1)
  target_compile_options(compiler_options INTERFACE -g -O1)
else()
  target_compile_options(compiler_options INTERFACE -O3)
endif()

if(ENABLE_ALL_STATIC)
    # Setting linker flags to enable static binaries
    set(CMAKE_EXE_LINKER_FLAGS_INIT "-static" CACHE STRING "Initial linker flags.")
    # Prioritize static libraries over shared ones
    set(CMAKE_FIND_LIBRARY_SUFFIXES ".a" CACHE STRING "Library suffixes" FORCE)
    # Inform the user about the static build
    message(STATUS "Configured to build completely static binaries.")
endif()
