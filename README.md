# Graph Algorithms Visualizer

A desktop Java Swing application for building graphs by hand and visually stepping through classic graph algorithms: Breadth-First Search, Depth-First Search, Dijkstra's Algorithm, and Prim's Algorithm, with animated highlighting of each vertex as it's visited.

## Features

- Interactive graph builder: click to add vertices, connect them with weighted edges, and remove either at any time.
- Step-by-step algorithm animation: running an algorithm doesn't just print a result. Each visited vertex lights up in sequence (one every 0.7 seconds) so you can watch the algorithm's logic unfold in real time.
- Four built-in algorithms:
  - Breadth-First Search (BFS)
  - Depth-First Search (DFS)
  - Dijkstra's Algorithm (shortest paths from a source vertex)
  - Prim's Algorithm (minimum spanning tree)
- Live result display: once the animation finishes, the final traversal path, shortest-path distances, or MST edges are shown on screen.

## How It Works

Each algorithm implementation records the order in which it visits or finalizes vertices during its run. The UI layer (Graph.java) takes that recorded order and steps through it on a Swing Timer, highlighting one vertex per tick before revealing the algorithm's final text output. This keeps the algorithm logic and the animation logic separate.

## Getting Started

### Prerequisites
- JDK 25 or newer
- Maven (or an IDE with built-in Maven support, such as NetBeans or IntelliJ IDEA)

### Running the project

1. Clone the repo  
2. Build and run with Maven

### Usage

1. Select "Add a Vertex" mode and click anywhere on the canvas to place a vertex; enter a single-character ID when prompted.
2. Select "Add an Edge" mode and click two vertices in sequence to connect them; enter a weight when prompted.
3. Choose an algorithm from the menu.
4. Click a starting vertex, then watch the visited vertices highlight in order and read the result at the bottom of the window.

## Project Structure
src/main/java/
algorithms/
- GraphAlgorithm.java (common interface for all algorithms)
-BFSAlgorithm.jav
-DFSAlgorithm.java
-DijkstrasAlgorithm.java
- PrimsAlgorithm.java
-AlgorithmSetter.java (runs the selected algorithm)
visualizer/
- GraphVisualizer.java (application entry point)
- MainFrame.java (main window and menu setup)
- Graph.java (canvas, mouse handling, animation)
- Vertex.java (vertex UI component and highlight state)
- Edge.java (edge UI component)
- Mode.java (interaction mode enum)

## Built With

- Java (Swing)
- Maven
