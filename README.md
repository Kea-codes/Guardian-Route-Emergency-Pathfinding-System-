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
