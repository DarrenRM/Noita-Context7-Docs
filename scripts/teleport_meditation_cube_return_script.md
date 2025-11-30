---
title: Teleport Meditation Cube Return Script
category: scripts
---

# Teleport Meditation Cube Return Script

This script controls the visual effects and teleportation behavior of the "Meditation Cube" building in Noita. It dynamically animates the cube's visual components and manages its teleportation destination.

## Key Functionality

### Visual Animation

The script animates a set of visual effects (FX entities) that form the "cube." This animation involves:

*   **Shape Definition:** It uses a predefined set of vertices (`verts`) to define the shape of the visualizer. The current default is an octahedron.
*   **Rotation:** The vertices are rotated around the Y and X axes based on the game's frame number (`time`) to create a dynamic, spinning effect.
*   **Vertex Interpolation:** For each frame, two random vertices from the shape are selected. The visual FX entities are then positioned along the line segment connecting these two vertices, creating a "trail" or "beam" effect. The `pos` variable (derived from `time % 2`) causes the FX entities to alternate between the two selected vertices, creating a pulsing or shifting appearance.
*   **Scaling and Positioning:** The interpolated vertex positions are scaled and then offset by the cube's own position (`pos_x`, `pos_y`) to place the visual effects correctly in the game world.

### Teleportation Logic

The script also handles setting the return coordinates for the teleportation component associated with the cube.

*   **Periodic Update:** The teleportation destination is updated periodically (every 71 frames).
*   **Default Coordinates:** It retrieves default teleportation coordinates from the `TeleportComponent` if available.
*   **Global Overrides:** It then attempts to override these coordinates using global variables: `TELEPORT_MEDITATION_CUBE_POS_X` and `TELEPORT_MEDITATION_CUBE_POS_Y`. This allows for external configuration of the teleportation destination.
*   **Component Update:** Finally, it updates the `TeleportComponent` with the determined `teleport_back_x` and `teleport_back_y` values.

## Key Attributes and Elements

| Attribute/Element        | Description