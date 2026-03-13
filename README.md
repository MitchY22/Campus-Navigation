# Campus Navigation Application

A Java-based command-line application that computes the shortest walking paths between campus buildings using **Dijkstra’s algorithm**. The program loads a campus graph dataset and allows users to explore campus connectivity, view graph statistics, and compute optimal routes between locations.

This project demonstrates graph data structures, file parsing, and shortest-path algorithms applied to a real-world campus navigation problem.

---

## Project Overview

This application models a university campus as a **weighted graph**:

- **Nodes** represent campus buildings
- **Edges** represent walking paths between buildings
- **Weights** represent travel time in seconds

The program loads this data from a `.dot` graph file and computes optimal routes between buildings using **Dijkstra’s shortest path algorithm**.

---

## Features

- Compute the **shortest walking path** between two campus buildings
- Parse and process **.dot graph files**
- Construct adjacency-list graph structures for pathfinding
- Display graph statistics such as node and edge counts
- Interactive **command-line interface** for user input

---

## Technologies Used

- Java
- Graph Data Structures
- Dijkstra’s Shortest Path Algorithm
- File Parsing
- Command-Line Interface (CLI)

---

## Project Structure

```text
Backend.java
BackendInterface.java
Frontend.java
FrontendInterface.java
DijkstraGraph.java
BaseGraph.java
GraphADT.java
MapADT.java
ShortestPathResult.java
ShortestPathResultInterface.java
campus.dot
BUILDINGS.md
```

### Component Responsibilities

**Backend (My Contribution)**

- Implemented graph construction from `.dot` file data
- Implemented **Dijkstra’s shortest path algorithm**
- Calculated path metrics such as total distance and node count
- Designed backend architecture using Java interfaces
- Provided APIs used by the frontend

**Frontend (Partner Contribution)**

- Implemented command-line user interface
- Handled user input and output display
- Integrated backend pathfinding functionality into the user interface

---

## How the Algorithm Works

The program uses **Dijkstra’s algorithm** to compute the shortest path between two buildings.

Algorithm steps:

1. Initialize all node distances as infinity except the starting node.
2. Use a priority queue to process the closest unvisited node.
3. Update distances for neighboring nodes when shorter paths are found.
4. Continue until the destination node is reached.
5. Reconstruct the path using stored predecessor nodes.

This approach efficiently computes shortest paths in weighted graphs.

---

## Dataset

The campus map is stored in `campus.dot`, which defines a weighted graph using the DOT format.

Example entry:

```text
"Memorial Union" -- "Science Hall" [seconds=105.8];
```

This means:

- A walking path exists between **Memorial Union** and **Science Hall**
- The estimated travel time is **105.8 seconds**

The program parses this file and constructs the graph dynamically.

---

## Running the Application

### 1. Compile the program

From the project directory run:

```bash
javac *.java
```

### 2. Run the application

```bash
java Backend
```

---

## Using the Program

After launching the application, the program displays a menu with options to load the graph data, view graph statistics, and compute shortest paths.

### Step 1 — Load the graph dataset

Load the dataset by entering the option to read graph data, then input:

```text
campus.dot
```

### Step 2 — View graph statistics

Select the menu option for graph statistics to display information about the campus graph, including the number of nodes and edges.

### Step 3 — Compute a shortest path

Select the menu option for shortest path search, then enter the names of the starting and destination buildings.

Example:

```text
Enter the name of the starting building: 
Memorial Union
Enter the name of the destination building: 
Grainger Hall
The shortest path to Grainger Hall from Memorial Union is: [Memorial Union, Radio Hall, Education Building, South Hall, Law Building, Music Hall, Chadbourne Residence Hall, Vilas Communication Hall, Sellery Residence Hall, Grainger Hall]
```

---

## Valid Building Names

The application accepts building names from the `campus.dot` dataset.

For the full list of supported locations, see [BUILDINGS.md](BUILDINGS.md).

Example valid building names include:

- Memorial Union
- Wendt Commons
- Grainger Hall
- Union South
- Computer Sciences and Statistics
- Van Hise Hall
- Bascom Hall
- Camp Randall Stadium

---

## What I Learned

- Implementing **Dijkstra’s shortest path algorithm**
- Designing modular systems using **interfaces and abstraction**
- Parsing structured graph data from `.dot` files
- Constructing adjacency-list graph representations
- Integrating backend algorithm logic with a user interface

---

## Author

**Mitchell Young**  
Computer Science & Information Science  
University of Wisconsin–Madison
