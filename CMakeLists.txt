# CMakeList.txt : Top-level CMake project file, do global configuration
# and include sub-projects here.
#
cmake_minimum_required (VERSION 3.8)

project ("p3plus_hmi")

# Include sub-projects.
add_subdirectory ("hmi_app")
