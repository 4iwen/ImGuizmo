cmake_minimum_required(VERSION 3.6)
project(ImGuizmo LANGUAGES CXX)


set(IMGUI_PATH ${CMAKE_SOURCE_DIR}/deps/imgui)

find_path(IMGUI_INCLUDE_DIR imgui.h PATHS ${IMGUI_PATH} NO_DEFAULT_PATH)

if (IMGUI_INCLUDE_DIR)
    message(STATUS "ImGui found at ${IMGUI_INCLUDE_DIR}")
    include_directories(${IMGUI_INCLUDE_DIR})
else()
    message(FATAL_ERROR "ImGui not found. Please make sure it is located in ${IMGUI_PATH}")
endif()

add_library(
        ImGuizmo STATIC

        ImCurveEdit.cpp
        ImGradient.cpp
        ImGuizmo.cpp
        ImSequencer.cpp
        GraphEditor.cpp
)