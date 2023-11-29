[![Build Status](https://github.com/JustinBraben/OpenGL_CMake_Template/actions/workflows/ci/badge.svg)](https://github.com/JustinBraben/OpenGL_CMake_Template/actions)

# OpenGL C++ Project Template

This repository serves as a template for kickstarting a new OpenGL project using modern C++ and popular libraries like GLFW, GLM, and GLAD. The template utilizes CMake for project configuration and GitHub Actions for building on multiple platforms.

## Features

- **CMake Configuration:** The project is set up with CMake, providing a flexible and cross-platform build system. You can easily configure and extend the project using CMake.

- **GLFW, GLM, and GLAD:** The template includes CMake's `FetchContent` to automatically download and integrate GLFW, GLM, and GLAD into your project. These libraries are fundamental for OpenGL development.

- **Modern C++:** The project is structured to encourage modern C++ practices. Feel free to use features from C++11 and beyond to write clean and efficient code.

- **GitHub Actions:** The repository is configured with GitHub Actions for continuous integration. The provided workflows ensure that your project builds successfully on multiple platforms, giving you confidence in its cross-platform compatibility.

## Getting Started

1. **Clone the Repository:**

    ```bash
    git clone https://github.com/your-username/your-opengl-project.git
    cd your-opengl-project
    ```

2. **Build the Project:**

    ```bash
    mkdir build
    cd build
    cmake ..
    make
    ```

3. **Run the Project:**

    Execute the generated executable in the build directory.

    ```bash
    ./your_opengl_project
    ```

## Directory Structure

- `src/`: This directory contains the source code for your OpenGL project.
- `CMakeLists.txt`: The main CMake configuration file for your project.
- `.github/workflows/`: GitHub Actions workflows for building the project on various platforms.

## Customization

- **Add Your Source Files:** Place your C++ source files in the `src/` directory.
- **Extend CMake Configuration:** Modify `CMakeLists.txt` to include additional libraries or configure project-specific settings.

## GitHub Actions

The repository is set up with GitHub Actions to automatically build your project on Linux, macOS, and Windows with each push. Check the `.github/workflows/` directory for workflow configurations.

## Contributing

Feel free to open issues or pull requests for any improvements, bug fixes, or features you'd like to contribute.

## License

This project is licensed under the MIT License - see the [LICENSE](https://github.com/JustinBraben/OpenGL_CMake_Template/blob/master/LICENSE.txt) file for details.
