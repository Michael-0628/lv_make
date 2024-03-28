# CMakeList.txt : CMake project for lv_cmake, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

# Add source to this project's executable.
#add_executable (lv_cmake "lv_cmake.cpp" "lv_cmake.h")

FILE (GLOB_RECURSE SOURCES ./*.c ./*.cpp)

add_executable (lv_cmake ${SOURCES})

add_subdirectory(lvgl)
add_subdirectory(lv_drivers)

target_link_libraries(lv_cmake PRIVATE lvgl::lvgl lvgl::demos lvgl::examples lvgl::drivers)
target_include_directories(lv_cmake PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})

# Specify path to own LVGL config header
set(LV_CONF_PATH
    ${CMAKE_CURRENT_SOURCE_DIR}/lv_conf.h
    CACHE STRING "" FORCE)

# TODO: Add tests and install targets if needed.
