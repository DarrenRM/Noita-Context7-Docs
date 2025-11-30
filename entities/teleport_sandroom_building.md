---
title: Teleport Sandroom Building
category: entities
---

# Teleport Sandroom Building

This entity defines a specific type of teleportation building, likely used in the "sandroom" context within Noita. It inherits its base functionality from a generic `teleport.xml` file and customizes its destination.

## Key Components

### Base Entity

*   **Inheritance:** Inherits core functionality from `data/entities/buildings/teleport.xml`. This means it will have the fundamental properties and behaviors of a standard teleport.

### UI Info Component

*   **`name`**: `$teleport_back`
    *   This likely defines the in-game name or identifier for this specific teleport, possibly indicating it's a return point.

### Teleport Component

*   **`target_x_is_absolute_position`**: `0`
    *   Indicates that the `target.x` coordinate is an absolute position within the game world, not relative to the teleport's current location.
*   **`target.x`**: `-460`
    *   The absolute X-coordinate for the teleport destination.
*   **`target.y`**: `150`
    *   The absolute Y-coordinate for the teleport destination.

This configuration suggests a fixed teleport destination, likely a specific room or area designated as the "sandroom" or a return point from it.