# 🗺️ Pathfinding Simulator: Dijkstra & A* (Processing)

[![Project Status](https://img.shields.io/badge/status-completed-green.svg)]()
[![Technology](https://img.shields.io/badge/technology-Processing%20%2F%20Java-blue.svg)]()

> An interactive autonomous pathfinding simulator developed in Processing, designed to calculate optimized movement routes using **Dijkstra** and **A\*** algorithms across complex terrains with dynamic obstacles and inventory mechanics.

---

## 🎯 About the Project

This academic project implements and visualizes classical graph search algorithms applied to a grid-based map featuring varying terrain costs, static obstacles, and interactive items. The system dynamically computes the fastest route while managing movement speed penalties and resource acquisition (such as a boat for water navigation).

---

## 🚀 Features and Game Rules

### 🕹️ Player & Movement System
* **Player Class:** Manages real-time attributes including spatial coordinates, movement speed, and inventory status (boat possession indicator).
* **Mouse Interaction:** The player autonomously navigates from its current location to any clicked destination on the map.
* **Camera Control:** Pressing the **`P`** key instantly centers the viewport on the player's current position.

### 🌿 Terrains and Cost Mechanics
Different surfaces alter both the player's movement speed and the edge weights inside the underlying graph:

| Terrain | Player Speed | Dijkstra Edge Weight |
| :--- | :--- | :--- |
| **Grass** | 1 block / second | `2` |
| **Sand** | 0.5 blocks / second (Half speed) | `3` |
| **Water (With Boat)** | 2 blocks / second (Double speed) | `1` |
| **Water (Without Boat)** | *Impassable* | `Infinity` |

* **Static Obstacles:** Non-traversable elements such as rocks, cacti, and corals block any pathing attempts.
* **Boat Mechanic:** A boat spawns randomly on the map within a 100-block radius of the player's initial spawn, unlocking water pathways upon collection.

---

## 🧠 Architecture & Algorithms

1. **Graph Modeling:** The map is structured as a grid where each tile acts as a graph vertex. Edge weights between adjacent vertices are determined by calculating the average weight of both connected tiles.
2. **Dijkstra's Algorithm:** Implemented to guarantee the absolute shortest path based on cumulative weighted costs.
3. **A\* Algorithm (Bonus Optimization):** Optional heuristic implementation utilizing Manhattan or Euclidean distance calculations to optimize search performance.

---

## 📂 Repository Structure

```text
├── PathfindingSimulator/     # Main Processing sketch folder
│   ├── PathfindingSimulator.pde # Core logic, drawing loop, and event handling
│   ├── Player.pde           # Player class and movement logic
│   ├── Dijkstra.pde         # Graph creation and pathfinding algorithms
│   └── Map.pde              # Grid management and rendering
├── data/                    # Images, sprites, and assets
└── README.md                # Project documentation
