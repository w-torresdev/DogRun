cmake_minimum_required(VERSION 3.10)
project(DogRun)

set(CMAKE_CXX_STANDARD 17)

find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)

include_directories(include)

file(GLOB_RECURSE SOURCES
    src/*.cpp
    src/*.c
)

add_executable(DogRun ${SOURCES})

target_link_libraries(DogRun
    OpenGL::GL
    glfw
)

file(COPY ${CMAKE_SOURCE_DIR}/src/shaders
     DESTINATION ${CMAKE_BINARY_DIR})

file(COPY ${CMAKE_SOURCE_DIR}/src/textures
     DESTINATION ${CMAKE_BINARY_DIR})
