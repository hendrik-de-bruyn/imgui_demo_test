cmake_minimum_required(VERSION 3.0.0)
project(imgui_demo_test VERSION 0.0.0)

set(OpenGL_GL_PREFERENCE GLVND)
find_package(OpenGL REQUIRED)
#find_package(glfw3 3.3 REQUIRED)

set(CMAKE_CXX_FLAGS)

include_directories(lib/glfw/include)
include_directories(lib/imgui)

set(IMGUI_SOURCES
        lib/imgui/imgui.cpp
        lib/imgui/imgui_demo.cpp
        lib/imgui/imgui_draw.cpp
        lib/imgui/imgui_impl_glfw.cpp
        lib/imgui/imgui_impl_opengl3.cpp
        lib/imgui/imgui_tables.cpp
        lib/imgui/imgui_widgets.cpp
        )
set(SOURCE_FILES main.cpp ${IMGUI_SOURCES})

add_executable(imgui_test ${SOURCE_FILES})

target_link_libraries(imgui_test OpenGL::GL)
target_link_libraries(imgui_test glfw)