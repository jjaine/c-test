# Testing C code with GoogleTest

A sample project about testing C code with [GoogleTest](https://github.com/google/googletest). Used the [Quickstart guide](https://google.github.io/googletest/quickstart-cmake.html) for building with CMake as a reference. 

## Prerequisites
- CMake (for macOS install from [Homebrew](https://brew.sh/) with `brew install cmake`)
- C compiler (for macOS included with Xcode)

## How-to
1. Make `build` directory with `mkdir build`.
2. Build the `main` and tests with
```
cmake -S . -B build
cmake --build build
```
3. Go into the build directory with `cd build`.
    - Run `main` with `./main`.
    - Run tests with `ctest`.

## C programming 101
- `main.c` for the main function
- `source.h` for defining interfaces (name as you wish)
    * Remember to use [include guards](https://en.wikipedia.org/wiki/Include_guard)! :)
- `source.c` for implementing the functions

## Testing
- Write tests into `test` folder, use `.cc` file extension
- Modify `CMakeLists.txt` as needed when changing the source and test file names
- C source files need to be included inside `extern "C"`.
- [Assertions list](https://google.github.io/googletest/reference/assertions.html) in GoogleTest documentation