cmake_minimum_required(VERSION 3.20)
set(CMAKE_CXX_STANDARD 17)

project(ImGui)

# Define the path to ImGui header files
set(IMGUI_HEADERS
        imconfig.h
        imgui.h
        imgui_internal.h
        imstb_rectpack.h
        imstb_textedit.h
        imstb_truetype.h
)

# Define the path to ImGui source files
set(IMGUI_SOURCES
        imgui.cpp
        imgui_draw.cpp
        imgui_widgets.cpp
        imgui_demo.cpp
        imgui_tables.cpp
        backends/imgui_impl_opengl3.cpp
        backends/imgui_impl_glfw.cpp
)

# Create a library target for ImGui
add_library(imgui ${IMGUI_HEADERS} ${IMGUI_SOURCES})

# Set include directories for ImGui
target_include_directories(imgui
        PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
        PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/../glfw/include)
