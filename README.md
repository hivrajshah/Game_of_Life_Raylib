#  Conway's Game of Life — C++ & Raylib

A real-time interactive simulation of **Conway's Game of Life** built in C++ using the [Raylib](https://www.raylib.com/) graphics library. Watch cellular automata evolve, die, and regenerate — all driven by just four simple rules.

---

##  About

A grid simulation running at dynamic FPS with full mouse and keyboard control.

---

##  The Four Rules

| Rule | Condition | Outcome |
|------|-----------|---------|
| **Underpopulation** | Live cell with < 2 live neighbours | Dies |
| **Stasis** | Live cell with 2 or 3 live neighbours | Survives |
| **Overpopulation** | Live cell with > 3 live neighbours | Dies |
| **Regeneration** | Dead cell with exactly 3 live neighbours | Becomes alive |

---

##  Controls

| Key / Action | Description |
|---|---|
| `Left Mouse Click` | Toggle a cell on/off |
| `Enter` | Start the simulation |
| `Space` | Pause the simulation |
| `R` | Fill grid with a random state |
| `C` | Clear the grid |
| `F` | Increase FPS (speed up) |
| `S` | Decrease FPS (slow down) |

---

## 🏗️ Project Structure

```
├── main.cpp          # Entry point, window setup, game loop
├── simulation.cpp    # Core Game of Life logic & update rules
├── simulation.hpp    # Simulation class declaration
├── grid.cpp          # Grid rendering and cell manipulation
├── grid.hpp          # Grid class declaration
└── Makefile          # Build configuration
```

---

##  Concepts & Technologies Used

### Language & Build
- **C++17** — core language
- **Makefile** — build automation

### C++ Concepts Practiced
- **Header files (`.hpp`)** — separating declarations from definitions for clean modular design
- **Classes & Constructors** — `Grid` and `Simulation` classes with initializer list constructors
- **`std::vector`** — 2D grid stored as `vector<vector<int>>` for dynamic sizing
- **`std::pair` & `std::vector<std::pair<int,int>>`** — used to store the 8 neighbour offset directions compactly
- **Range-based for loops with `const auto&`** — efficient, read-only iteration over neighbour offsets
- **Ternary operator** — concise conditional expressions for cell color and value assignment
- **Modular arithmetic** — wraps grid edges to create a toroidal (wrap-around) world
- **Encapsulation** — private data members with public getter/setter methods
- **Boolean state management** — `run` flag to start/stop simulation without data loss
- **Double-buffering** — `grid` + `tempGrid` pattern to avoid mid-frame mutation

### Raylib Functions Used
- `InitWindow()` / `CloseWindow()` — window lifecycle
- `SetTargetFPS()` — frame rate control
- `BeginDrawing()` / `EndDrawing()` — render frame
- `ClearBackground()` — screen clear each frame
- `DrawRectangle()` — rendering each cell on the grid
- `IsMouseButtonDown()` / `GetMousePosition()` — mouse input handling
- `IsKeyPressed()` — keyboard event detection
- `GetRandomValue()` — seeding random initial cell states
- `SetWindowTitle()` — dynamic title to reflect simulation state
- `WindowShouldClose()` — main loop condition

---

##  Getting Started

### Prerequisites
- [Raylib](https://www.raylib.com/) installed
- G++ compiler with C++17 support

### Build & Run
```bash
make
./main.exe
```

---

##  What I Learned

This project was a hands-on dive into:
- Structuring a C++ project across multiple files using header/source separation
- Using STL containers (`vector`, `pair`) for clean data modelling
- Integrating a real-time graphics library (Raylib) for interactive simulation
- Implementing a classic cellular automaton algorithm with efficient double-buffering

---

##  License

Open-source and free to use for learning purposes.
