---
title: Lava Lake Teleport
category: entities
---

# Lava Lake Teleport

This entity defines a specific teleportation point within the game world, designed to transport players to a lava lake area. It inherits its core functionality from a generic `teleport.xml` entity.

## Key Components

### `Base`
Inherits from `data/entities/buildings/teleport.xml`, providing the fundamental teleportation behavior.

### `UIInfoComponent`
*   **`name`**: `$teleport_back` - This likely refers to a localized string for the teleport's name displayed in the UI.

### `TeleportComponent`
This component dictates the destination of the teleport.
*   **`target_x_is_absolute_position`**: `0` - Indicates that the `target.x` value is an absolute coordinate, not relative to the player's current position.
*   **`target.x`**: `-1875` - The absolute X-coordinate for the teleport destination.
*   **`target.y`**: `0` - The absolute Y-coordinate for the teleport destination.