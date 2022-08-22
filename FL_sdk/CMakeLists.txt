cmake_minimum_required (VERSION 3.5)

project(fl_lib LANGUAGES CXX)


add_library(${PROJECT_NAME}
    "include/fp_cplug.h"
    "include/fp_extra.h"
    "include/fp_pathmanager.h"
    "include/fp_plugclass.h"
    "include/fp_def.h"
    "include/generictransport.h"

    "src/fp_cplug.cpp"
    "src/fp_extra.cpp"
    "src/fp_pathmanager.cpp"
    "src/fp_plugclass.cpp"
)

set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 20)

target_include_directories(${PROJECT_NAME}
    PUBLIC
    $<INSTALL_INTERFACE:include/${PROJECT_NAME}>
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>

    PRIVATE
)

target_link_libraries(${PROJECT_NAME}
    PRIVATE
)