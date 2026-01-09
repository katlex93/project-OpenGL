cmake_minimum_required(VERSION 3.10)
project(OpenGLProject)

set(CMAKE_CXX_STANDARD 17)

# Path to GLFW
set(GLFW_DIR ${CMAKE_SOURCE_DIR}/../libs/glfw)

add_executable(OpenGLProject
    src/main.cpp
    src/glad.c
)

# GLFW headers
target_include_directories(OpenGLProject PRIVATE
    ${GLFW_DIR}/include
    ${CMAKE_SOURCE_DIR}/include
)

# GLFW + macOS frameworks
target_link_libraries(OpenGLProject
    ${GLFW_DIR}/lib-universal/libglfw3.a
    "-framework OpenGL"
    "-framework Cocoa"
    "-framework IOKit"
    "-framework CoreVideo"
)


