cmake_minimum_required (VERSION 3.5)

project(saw_vc LANGUAGES CXX)

# add_executable(${PROJECT_NAME}
#     "src/FruityPlug.cpp"

#     "src/testplug.cpp"
#     "src/testplug.h"
# )

add_library(${PROJECT_NAME} MODULE     "src/FruityPlug.cpp"

"src/testplug.cpp"
"src/testplug.h")

set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 20)

target_include_directories(${PROJECT_NAME}
    PUBLIC
    $<INSTALL_INTERFACE:include/${PROJECT_NAME}>
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>

    PRIVATE
)

target_link_libraries(${PROJECT_NAME}
    PUBLIC
    fl_lib
)