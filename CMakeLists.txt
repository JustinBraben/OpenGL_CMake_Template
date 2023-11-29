# Specify the minimum required CMake version
cmake_minimum_required(VERSION 3.16)

# Set the variable projectName to what you want your project to be called
set(projectName "OpenGL_CMake_Template")

# Declare the project with the specified language (C++)
project(${projectName} LANGUAGES CXX)

# Set the output directory for executables to bin/
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

# Define an option to build shared libraries (default is OFF)
option(BUILD_SHARED_LIBS "Build shared libraries" OFF)

# Define an option to choose between static and shared GLEW library (default is static)
# option(USE_GLEW_STATIC "Use static GLEW library" ON)

# Include FetchContent module for managing external dependencies
include(FetchContent)
set(FETCHCONTENT_QUIET FALSE)

# Fetch and declare glfw as an external dependency
FetchContent_Declare(
    glfw
    GIT_REPOSITORY https://github.com/glfw/glfw.git
    GIT_TAG 3.3-stable
    GIT_SHALLOW TRUE
    GIT_PROGRESS TRUE
)
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(GLFW_INSTALL OFF CACHE BOOL "" FORCE)
FetchContent_MakeAvailable( glfw )

# Fetch and declare glm as an external dependency
FetchContent_Declare(
    glm
    GIT_REPOSITORY https://github.com/g-truc/glm.git
    GIT_TAG origin/master
    GIT_SHALLOW TRUE
    GIT_PROGRESS TRUE
)
FetchContent_MakeAvailable( glm )

# Fetch and declare GLAD as an external dependency
FetchContent_Declare(
    glad
    GIT_REPOSITORY https://github.com/Dav1dde/glad.git
    GIT_TAG        origin/master
    GIT_SHALLOW TRUE
    GIT_PROGRESS TRUE
)

FetchContent_MakeAvailable( glad )

FetchContent_GetProperties(glad)

# Debug info on where the binary directory is
message(STATUS "Binary directory: ${CMAKE_BINARY_DIR}")

# Create an executable target named "flappy" with the source file src/main.cpp
add_executable(${projectName} src/main.cpp)

# Link the executable against glfw, glm, and glew libraries based on the selected option
#if(USE_GLEW_STATIC)
#    target_link_libraries(${projectName} PRIVATE glfw glm::glm libglew_static)
#else()
#    target_link_libraries(${projectName} PRIVATE glfw glm::glm libglew_shared)
#endif()

target_link_libraries(${projectName} PRIVATE glfw glm::glm glad)

# Set the C++ standard to C++17 for the "flappy" target
target_compile_features(${projectName} PRIVATE cxx_std_17)

# Install the "flappy" target
install(TARGETS ${projectName})