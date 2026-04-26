# Project README

## Overview
This project is a simulation of flocking behavior in birds using C/C++ and a graphical library. The main focus is on the interaction between individual "birds" (represented as simple entities moving according to certain rules) and their environment.

## Features
- **Flocking Behavior**: Birds follow simple rules to maintain alignment, cohesion, and separation.
- **User Interaction**: Users can control a bird with the mouse.
- **Cross-Platform Compilation**:
  - Linux
  - Windows
  - Wine (Linux cross-compilation for Windows)
  - WebAssembly

## Project Structure
```
Gui_Boids/
├── build/              # .exe files produced by Main.c
├── src/                # Source code
│   ├── Main.c          # Entry point
│   └── *.h             # Standalone Header-based C-files, without *.c files that implement it
├── Makefile.linux      # Linux Build configuration
├── Makefile.windows    # Windows Build configuration
├── Makefile.wine       # Wine Build configuration
├── Makefile.web        # Emscripten Build configuration
└── README.md           # This file
└── LICENSE
└── .gitignore
```

### Prerequisites
- C/C++ Compiler and Debugger (GCC, Clang)
- Make utility
- Standard development tools
- Libraries needed in specific projects:
  - Linux: X11 for GUI, PNG and JPEG for image handling
  - Windows: user32, gdi32, winmm
  - Wine: No additional libraries required
  - WebAssembly: emcc (Emscripten compiler)

## Build & Run

### Linux
```sh
cd Gui_Boids
make -f Makefile.linux all
./build/Main
```

### Windows
```sh
cd Gui_Boids
make -f Makefile.windows all
build\Main.exe
```

### Wine (Linux Cross-Compile for Windows)
```sh
cd Gui_Boids
make -f Makefile.wine all
WINEPREFIX=~/wine64 WINEARCH=win64 wine build/Main.exe
```

### WebAssembly
```sh
cd Gui_Boids
make -f Makefile.web all
emrun --no_browser --port 8080 build/index.html
```

# Build Steps
- `make -f Makefile.(os) all`: Compiles the project and generates the executable.
- `make -f Makefile.(os) do`: Compiles the project, generates the executable, and runs it.
- `make -f Makefile.(os) clean`: Removes build artifacts to prepare for a clean rebuild.

# Build Options
- `make -f Makefile.(os) all` or `make -f Makefile.(os) do` builds the output.
- `make -f Makefile.(os) clean` removes build artifacts for a clean rebuild.