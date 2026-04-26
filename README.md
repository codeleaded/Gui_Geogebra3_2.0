# Project README

## Overview
This project is a simple C-based application that demonstrates basic 3D graphics rendering, camera controls, and projection matrix calculations. It uses standard C libraries for development and is designed to be built on multiple platforms using different makefiles.

## Features
- Basic 3D transformations (translation, rotation)
- Camera movement and orientation control
- Perspective projection matrix generation
- Triangle clipping against a plane

## Project Structure
```
<Project>/
├── build/              # .exe files produced by Main.c
├── libs/               # *.c for bin
├── src/                # src code
│   ├── Main.c          # Entry point
│   └── utils.h         # Standalone header-based C-files, without *.c files that implement it
├── Makefile.linux      # Linux Build configuration
├── Makefile.windows    # Windows Build configuration
├── Makefile.wine       # Wine Build configuration
├── Makefile.web        # Emscripten Build configuration
└── README.md           # This file
```

### Prerequisites
- C/C++ Compiler and Debugger (GCC, Clang)
- Make utility
- Standard development tools

## Build & Run
To build and run the project on Linux:
```sh
cd <Project>
make -f Makefile.linux all
./build/Main
```

For Windows:
```sh
cd <Project>
make -f Makefile.windows all
.\build\Main.exe
```

For cross-compiling to Windows using Wine on Linux:
```sh
cd <Project>
make -f Makefile.wine all
./build/Main.exe
```

To build and run the project for WebAssembly using Emscripten:
```sh
cd <Project>
make -f Makefile.web all
python3 -m http.server 8000
# Open browser and navigate to http://localhost:8000/build/index.html
```

Build Options
- `make -f Makefile.(os) all`: Build output.
- `make -f Makefile.(os) do`: Build + executable output.
- `make -f Makefile.(os) clean`: Remove build artifacts.