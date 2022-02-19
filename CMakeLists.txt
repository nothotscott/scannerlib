
project(scannerlib C)
cmake_minimum_required(VERSION 3.8)
include(CTest)

# Find dependencies

function(bundle_library lib_name inc_name)
	find_library(lib${lib_name} ${lib_name} REQUIRED)
	find_path(inc${inc_name} ${inc_name} REQUIRED)
	include_directories(${inc${inc_name}})
	message(STATUS "Found ${lib_name} library ${lib${lib_name}}")
	message(STATUS "Found ${inc_name} headers ${inc${inc_name}}")
endfunction()

bundle_library(liquid liquid)
bundle_library(mbe mbelib.h)

# Compile
include_directories(include)

add_subdirectory(src)
add_subdirectory(test)

enable_testing()
