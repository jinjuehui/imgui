# usage:
# cmake -B build
# cmake --build build

cmake_minimum_required(VERSION 3.15)
project(ImGui LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)

set(IMGUI_SOURCES
    imgui.cpp
    imgui_draw.cpp
    imgui_tables.cpp
    imgui_widgets.cpp
    backends/imgui_impl_dx12.cpp
    backends/imgui_impl_win32.cpp
)

add_library(imgui STATIC ${IMGUI_SOURCES})

target_include_directories(imgui PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/backends
)