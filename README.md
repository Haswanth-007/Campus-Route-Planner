Campus Route Planner
====================

This is my Data Structures and Algorithms project: a Campus Route Planner. 

The core idea is pretty straightforward. We've all needed to find the quickest way to get from one building to another before a class starts. This program models the campus map as a graph and uses pathfinding algorithms like Dijkstra's and Breadth-First Search (BFS) to calculate the absolute shortest walking paths between different locations.

Below is a breakdown of how the project is organized and what each file actually does.

1. The Graph Structure (graph.hpp & graph.cpp)
This is the foundation of the project. It sets up the graph data structure using an adjacency list. 
- The nodes (vertices) represent the different locations on campus, like lecture halls, gates, or the library.
- The edges represent the actual walking paths between them, and the edge "weight" is the physical distance of that path.

2. The Pathfinding Algorithms (dijkstra.hpp & dijkstra.cpp)
This is where the actual logic and math happen. I implemented a few different ways to navigate the campus:
- Standard Dijkstra: This calculates the absolute shortest path based on the walking distance.
- Edge-Avoiding Dijkstra: This is a fallback feature. If a specific path is blocked (for example, due to construction or an event), this algorithm finds the next best route without using that specific blocked road.
- Breadth-First Search (BFS): Instead of looking at the distance, this finds the path with the fewest number of stops or intersections. 
- Connectivity Check (isConnected): A utility function that scans the graph to make sure the map data is valid and that no building is completely isolated from the rest of the campus.

3. File Handling and Data Parsing (io.hpp & io.cpp)
The algorithms need data to work with, so these files handle reading the campus map from a saved text file. They take human-readable location names (like "Cafeteria" or "Tech_Block") and translate them into numerical IDs that the C++ graph algorithms can easily process.

4. The Main Application (main.cpp)
This ties everything together. It acts as the main entry point to load up the campus map, take in the user's start and end locations, run the required algorithm, and print out the best route.


One-Line Description
--------------------
📂 Project Structure & File Workflow
--------------------

1.src/main.cpp: Runs the main user menu (CLI) and handles all user input.

2.src/graph.hpp / graph.cpp: Defines the core graph data structure (Adjacency List) to represent the campus map.

3.src/dijkstra.hpp / dijkstra.cpp: Implements the pathfinding algorithms (Dijkstra's, BFS) and connectivity checks.

4.src/io.hpp / io.cpp: Contains functions to read and parse the campus_map.txt file.

5.data/campus_map.txt: The input data file that defines all locations (nodes) and roads/paths (edges) with their distances.


How to Build and Run
--------------------

1. Build Command

Open your terminal and run the following g++ command from the project's root directory:
g++ src/*.cpp -o campus_planner -std=c++17


2. Run the Program

After building, run the compiled executable:
./campus_planner


This will start the interactive menu in your terminal.
