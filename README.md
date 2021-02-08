# C, Cmake and SDL2 Boilerplate ![CI](https://github.com/rafaeldelboni/c-cmake-sdl2-boilerplate/workflows/CI/badge.svg)

This is a C project template with the following features:

 - CMake build scripts for building libraries, applications, and tests.
 - Integrated with [DownloadProject](https://github.com/Crascit/DownloadProject) for lib dependencies like [Unity](https://github.com/rafaeldelboni/c-cmake-sdl2-boilerplate/blob/main/CMakeLists.txt#L11-L17).
 - Integrated with [Unity unit test framework](https://github.com/ThrowTheSwitch/Unity).
 - Integrated with [SDL2](https://www.libsdl.org/).
 - Integrated with [SDL2 Image](https://www.libsdl.org/projects/SDL_image/).
 - Resource folder to include assets
 - Updated and simplified version of [C-project-template](https://github.com/peterdn/C-project-template)

## Usage

### Build
```bash
# Debug build
make 
# Release build
make release
```

### Run Tests
This will build and run unity tests
```bash
make test
```

### Clean
This will delete generated files for debug and release
```bash
make clean
```

### Run Binary
This will open an SDL black window with the unlicense logo on it for 3 seconds.
```bash
# Debug bin
./build/debug/bin/example_app
# Release bin
./build/release/bin/example_app
```

## Directory Structure
```
./
├── .github
│   └── workflows -- Github workflows folder.
├── app -- Application source code
├── build
│   ├── cmake -- Cmake Finders for external compiled libs.
│   ├── debug -- Cmake debug build generated files.
│   │   ├── bin -- Application debug binaries.
│   │   └── resources -- Application resources assets symbolic link.
│   └── release -- Cmake release build generated files.
│       ├── bin -- Application release binaries.
│       └── resources -- Application resources assets symbolic link.
├── resources -- Application resources assets folder.
├── src -- Library source code and headers.
└── test -- Test source code.
    └── unity -- Unity test framework source.
```

## Dependencies
 - [Clang](https://clang.llvm.org/)
 - [Make](https://www.gnu.org/software/make/)
 - [CMake](https://cmake.org/)
 - [SDL2](https://www.libsdl.org/)
 - [SDL2 Image](https://www.libsdl.org/projects/SDL_image/)

### Installing Dependencies

#### Arch Linux
```bash
pacman -Sy clang cmake sdl2 sdl2_image
```

#### Ubuntu
```bash
sudo add-apt-repository -y "deb http://archive.ubuntu.com/ubuntu `lsb_release -sc` main universe restricted multiverse"
sudo apt-get update -y -qq
sudo apt-get install clang cmake libsdl2-dev libsdl2-image-dev
```

## License
This is free and unencumbered software released into the public domain.  
For more information, please refer to <http://unlicense.org/>
