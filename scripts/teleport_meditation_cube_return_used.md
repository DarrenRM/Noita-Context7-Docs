---
title: Teleport Meditation Cube Return Used
category: scripts
---

# Teleport Meditation Cube Return Used

This script defines the behavior when a player teleports using a meditation cube.

## Function: `portal_teleport_used`

This function is called when an entity teleports.

### Parameters:

*   `entity_teleported`: The entity that was teleported.
*   `from_x`: The X-coordinate of the starting position.
*   `from_y`: The Y-coordinate of the starting position.
*   `to_x`: The X-coordinate of the destination position.
*   `to_y`: The Y-coordinate of the destination position.

### Logic:

1.  **Player Check**: It first checks if the `entity_teleported` is a player.
2.  **Meditation Cube Effect Removal**: If it's a player, it iterates through all child entities of the player.
    *   If a child entity has the tag `"meditation_cube_effect"`, it is killed (removed from the game).
    *   The function then returns, preventing further execution for this teleport event.