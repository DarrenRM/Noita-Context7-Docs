---
title: Teleport Boss Arena
category: entities
---

# Teleport Boss Arena

This entity defines a teleportation point specifically designed for the boss arena. It inherits its base functionality from `teleport_liquid_powered.xml`.

## Key Components

### UIInfoComponent
This component defines the in-game name for the teleport.

*   **name**: `$teleport_deeper` - The internal identifier for the teleport's name, likely displayed in the UI.

### TeleportComponent
This component handles the teleportation logic.

*   **target\_x\_is\_absolute\_position**: `1` - Indicates that the `target.x` and `target.y` values represent absolute world coordinates.
*   **target.x**: `1891` - The absolute X-coordinate to which the player will be teleported.
*   **target.y**: `280` - The absolute Y-coordinate to which the player will be teleported.