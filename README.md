# libigl example project

A blank project example showing how to use libigl and cmake. Feel free and
encouraged to copy or fork this project as a way of starting a new personal
project using libigl.

## See the tutorial first

Install libigl
git clone https://github.com/libigl/libigl.git

Place this project right next to the libigl folder. For example, if libigl is installed in ~/foo/libigl, then you can create a copy of the this right next to it:
git clone https://github.com/libigl/libigl-demo.git ~/foo/libigl-demo

Read appleseed shaderball object
https://github.com/appleseedhq/shaderball

Extract the zip file to get the appleseed.obj


## Dependencies

The only dependencies are STL, Eigen, [libigl](http://libigl.github.io/libigl/) and the dependencies
of the `igl::opengl::glfw::Viewer` (OpenGL, glad and GLFW).
The CMake build system will automatically download libigl and its dependencies using
[CMake FetchContent](https://cmake.org/cmake/help/latest/module/FetchContent.html),
thus requiring no setup on your part.

To use a local copy of libigl rather than downloading the repository via FetchContent, you can use
the CMake cache variable `FETCHCONTENT_SOURCE_DIR_LIBIGL` when configuring your CMake project for
the first time:
```
cmake -DFETCHCONTENT_SOURCE_DIR_LIBIGL=<path-to-libigl> ..
```
When changing this value, do not forget to clear your `CMakeCache.txt`, or to update the cache variable
via `cmake-gui` or `ccmake`.

## Compile

Compile this project using the standard cmake routine:

    mkdir build
    cd build
    cmake ..
    make

This should find and build the dependencies and create a `example_bin` binary.

For ease of use you can copy the appleseed.obj file into the build folder but you can also directly reference it using terminal.


## Run

From within the `build` directory just issue:

    ./example appleseed.obj

A glfw app should launch displaying the obj files.
By deafult all faces will be white in color but when you click a face it will be changed to red.
The clicked face ID, assosciated Vertices ID and there world coordinates will be displayed on the terminal.
It will also genrate a "faces.txt" files containing the IDs of all faces which has been selected.
