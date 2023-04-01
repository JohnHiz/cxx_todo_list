# To-Do List

I started this project because OpeanAI told me to do it.

## Prerequisites

### Required packages

On Archlinux:
```bash
sudo apt install base-devel git cmake ninja
```

On Ubuntu:
```bash
sudo apt install base-essential git cmake ninja-build
```

On MacOS:
```bash
xcode-select --install
brew install git cmake ninja
```

## Downloading

```bash
git clone https://github.com/JohnVasil-ev/cxx_todo_list.git
```

## Configuration

```bash
cd cxx_todo_list
CMAKE_CONFIG=RelWithDebug   # Use Debug if you are a developer.
BUILD_DIR=build
cmake -S . -B ${BUILD_DIR} -DCMAKE_BUILD_TYPE=${CMAKE_CONFIG}
```

Optionally add `-DCMAKE_VERBOSE_MAKEFILE:BOOL=ON` to see the compile commands.
Also optionally, add `-GNinja` to the cmake arguments (this is what I am developing with).
Other build types are: `Release`, `RelWithDebInfo`, `Debug` and `BetaTest`.
See [stackoverflow](https://stackoverflow.com/questions/48754619/what-are-cmake-build-type-debug-release-relwithdebinfo-and-minsizerel/59314670#59314670) for an explanation of the different types.

## Building

```bash
NUMBER_OF_CPUS=$(($(grep '^cpu cores' /proc/cpuinfo | wc --lines) - 2))  # Linux
NUMBER_OF_CPUS=$(expr $(sysctl -n hw.ncpu) - 2)                          # MacOS

cmake --build ${BUILD_DIR} --config ${CMAKE_CONFIG} --parallel ${NUMBER_OF_CPUS}
```

Just set `NUMBER_OF_CPUS` to whatever you want, of course.
