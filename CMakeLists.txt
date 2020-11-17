cmake_minimum_required(VERSION 3.5)

project(OpenGL)

set(SOURCE_FILES src/main.cpp src/Renderer/Renderer.cpp src/VertexBuffer/VertexBuffer.cpp src/IndexBuffer/IndexBuffer.cpp)

add_executable(${PROJECT_NAME} ${SOURCE_FILES})

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(GLFW_INSTALL OFF CACHE BOOL "" FORCE)


add_subdirectory(Dependencies/GLFW)
add_subdirectory(Dependencies/GLEW/build/cmake)

target_link_libraries(${PROJECT_NAME} glfw)
target_link_libraries(${PROJECT_NAME} glew)