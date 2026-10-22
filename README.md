# rippercasted

> A modern C++ library — fast, sharp, and cast into reality.

A small, header-clean C++17 utility library. Built as a starting point you can extend with your own modules.

## Features

- Modern CMake 3.16+ build, C++17
- Header/source split — clean public API under `include/rippercasted/`
- Static library target with proper `rippercasted::rippercasted` alias
- Examples and tests wired in
- Install + package config targets (`find_package(rippercasted CONFIG)` ready)

## Project Layout

```
rippercasted/
├── CMakeLists.txt
├── cmake/
│   └── rippercastedConfig.cmake.in
├── include/
│   └── rippercasted/
│       └── rippercasted.hpp
├── src/
│   └── rippercasted.cpp
├── examples/
│   ├── CMakeLists.txt
│   └── demo.cpp
└── tests/
    ├── CMakeLists.txt
    └── test_basic.cpp
```

## Building

```bash
cmake -S . -B build -DCMAKE_BUILD_TYPE=Release
cmake --build build -j
```

## Running the demo

```bash
./build/examples/rippercasted_demo
```

## Running tests

Run CTest from the build directory for compatibility with CMake 3.16 and newer:

```bash
cmake -E chdir build ctest --output-on-failure
```

## Consuming in another project

After `cmake --install`, downstream projects can use:

```cmake
find_package(rippercasted CONFIG REQUIRED)
target_link_libraries(my_app PRIVATE rippercasted::rippercasted)
```

## License

MIT — see `LICENSE`.
