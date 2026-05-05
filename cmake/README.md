# CMake

> Cross-platform build system generator for C/C++ and beyond.

---

## What is CMake?

CMake is not a build system itself — it is a build system **generator**. It produces build files for your target platform (Makefiles on Linux, Visual Studio projects on Windows, Xcode on macOS) from a single `CMakeLists.txt` configuration.

---

## When to Use CMake

Use CMake when:
- You have a C/C++ project that needs to build on multiple platforms
- You're writing libraries that others will consume
- You need fine-grained control over compiler flags and linking
- You're working in embedded systems or game development

---

## Core Concepts

### CMakeLists.txt
```cmake
cmake_minimum_required(VERSION 3.20)
project(MyApp VERSION 1.0)

set(CMAKE_CXX_STANDARD 17)

add_executable(MyApp main.cpp utils.cpp)

target_include_directories(MyApp PUBLIC include/)
```

### Build Flow
```bash
mkdir build && cd build
cmake ..          # generate build files
cmake --build .   # compile
```

---

## Resources

- [CMake Official Docs](https://cmake.org/documentation/)
- [Modern CMake](https://cliutils.gitlab.io/modern-cmake/) — best free book on CMake
- [CMake Tutorial](https://cmake.org/cmake/help/latest/guide/tutorial/index.html) — official step-by-step
