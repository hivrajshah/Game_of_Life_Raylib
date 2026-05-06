# 🧬 Conway's Game of Life — C++ & Raylib

A real-time, interactive simulation of **Conway's Game of Life** built with **C++** and the **Raylib** graphics library. Watch cellular automata evolve, draw your own patterns, and control the simulation — all in a clean, performant desktop app.

---

## 🎮 Demo

> A 1000×1000 window with a 10px cell grid — 100×100 cells running live at configurable FPS.

---

## ✨ Features

- 🟢 **Live Cell Rendering** — Green cells on a dark background for crisp visibility
- 🖱️ **Interactive Drawing** — Click and drag to toggle cells manually
- ▶️ **Start / Stop** — Control the simulation at any time
- 🔀 **Random State** — Fill the grid with a random starting configuration
- 🗑️ **Clear Grid** — Reset everything to a blank slate
- ⚡ **FPS Control** — Speed up or slow down the simulation on the fly
- 🔁 **Wrap-around Grid** — Edges connect to the opposite side (toroidal topology)
- 🧱 **OOP Architecture** — Clean separation into `Grid` and `Simulation` classes

---

## 🕹️ Controls

| Key / Input         | Action                        |
|---------------------|-------------------------------|
| `Left Mouse Button` | Toggle cell alive/dead        |
| `Enter`             | Start simulation              |
| `Space`             | Stop simulation               |
| `R`                 | Randomize grid                |
| `C`                 | Clear grid                    |
| `F`                 | Increase FPS (+2)             |
| `S`                 | Decrease FPS (-2, min 5)      |

---

## 🏗️ Project Structure

```
├── main.cpp          # Entry point — window setup & game loop
├── simulation.hpp    # Simulation class interface
├── simulation.cpp    # Game of Life logic & update rules
├── grid.hpp          # Grid class interface
├── grid.cpp          # Grid rendering, cell manipulation
└── Makefile          # Build configuration
```

---

## 🧠 How It Works

The simulation follows the classic **Conway's Game of Life** rules:

1. A **live cell** with 2 or 3 live neighbours **survives**
2. A **dead cell** with exactly 3 live neighbours **becomes alive**
3. All other cells **die or stay dead**

Each frame, a `tempGrid` is used to compute the next generation without mutating the current state mid-update — ensuring correctness.

Neighbour counting uses **modular arithmetic** for seamless edge wrapping:
```cpp
int neighbourRow = (row + offset.first + grid.GetRows()) % grid.GetRows();
```

---

## 🛠️ Tech Stack

- **Language:** C++17
- **Graphics:** [Raylib](https://www.raylib.com/)
- **Build System:** Makefile (MinGW / GCC)
- **Platform:** Windows (`.exe`) — portable with bundled DLLs

---

## 🚀 Getting Started

### Prerequisites
- [Raylib](https://www.raylib.com/index.html) installed
- GCC / MinGW compiler

### Build & Run
```bash
make
./main.exe
```

Or just run the pre-built `main.exe` (Windows, includes required DLLs).

---

## 📚 What I Learned

- Object-oriented design in C++ (classes, constructors, member functions)
- 2D vector grids and double-buffering for simulation state
- Real-time rendering with Raylib
- Modular arithmetic for toroidal boundary conditions
- Makefile-based build systems

---

## 📄 License

This project is open source.

---

> *"The Game of Life is not your typical computer game. It is a cellular automaton."*
