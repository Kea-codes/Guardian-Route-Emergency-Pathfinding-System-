Overview
Java-based framework converting pixel images to navigable graphs with A* pathfinding and zone classification. Designed for evacuation planning and spatial analysis.

Core Components
Data Structures:

Point: Immutable 2D coordinate

Node: Graph vertex with position and edges

Edge: Connection between nodes with cost

ZoneType: WALKABLE, EXIT, DANGER, WALL

Interfaces:

IGraph<T>: Standard graph operations

IMap<K,V>: Minimal map contract

Algorithm:

AStarNode: Priority wrapper for A*

Graph: Main implementation with image processing

Key Features
Image Processing:

Converts pixels to graph nodes based on color

4 or 8-directional connectivity

Color-based zone classification with tolerance

Zone Classification:

EXIT: Green (RGB 14,111,34)

DANGER: Red (RGB 243,25,41)

WALL: Black

WALKABLE: Brightness > 0.3

Pathfinding:

A* algorithm with Manhattan heuristic

Dynamic costs by zone type

Danger avoidance (high cost for danger zones)

Nearest exit calculation

API Highlights
java
Graph(PixelReader, width, height, use8Directions)
aStar(Point start, Point goal) → List<Point>
findSafeEvacuationPath(Point start) → List<Point>
getZoneType(Point) → ZoneType
getAllZonesOfType(ZoneType) → List<Point>
Performance
O(V+E) space for graph storage

O(b^d) time for A* pathfinding

O(1) vertex/edge operations with HashMap

Early termination on goal reach

Use Cases
Evacuation route planning

Game AI navigation

Robotic path planning

Spatial analysis simulations

Dependencies
Java 8+

JavaFX (for PixelReader)

Design Principles
Immutable core types (Point)

Interface-based extensibility

Graceful error handling (null returns)

Configurable connectivity patterns
