# CMakeList.txt : CMake project for hmi_app, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

# Add source to this project's executable.
#add_executable (hmi_app "hmi_app.cpp" "hmi_app.h")

FILE (GLOB_RECURSE SOURCES ./*.c ./*.cpp)

add_executable (hmi_app ${SOURCES})

add_subdirectory(lvgl)
add_subdirectory(lv_drivers)

target_link_libraries(hmi_app PRIVATE lvgl::lvgl lvgl::demos lvgl::examples lvgl::drivers)
target_include_directories(hmi_app PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})

# Specify path to own LVGL config header
set(LV_CONF_PATH
    ${CMAKE_CURRENT_SOURCE_DIR}/lv_conf.h
    CACHE STRING "" FORCE)

# TODO: Add tests and install targets if needed.
