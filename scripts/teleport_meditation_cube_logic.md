---
title: Teleport Meditation Cube Logic
category: scripts
---

# Teleport Meditation Cube Logic

This script defines the behavior for the Teleport Meditation Cube, specifically handling player teleportation events.

## Key Functionality

The primary function `portal_teleport_used` is triggered when an entity is teleported by the cube. It focuses on player teleportation to manage the cube's state and apply special effects.

### `portal_teleport_used( entity_teleported, from_x, from_y, to_x, to_y )`

This function is called when a teleportation event occurs.

*   **`entity_teleported`**: The entity that was teleported.
*   **`from_x`, `from_y`**: The coordinates from which the entity was teleported.
*   **`to_x`, `to_y`**: The coordinates to which the entity was teleported.

#### Core Logic:

1.  **Player Check**: It first verifies if the `entity_teleported` is the player.
2.  **First Teleport Effect**:
    *   If this is the first time the player is using the Teleport Meditation Cube (checked by `GlobalsGetValue( "TELEPORT_MEDITATION_CUBE_POS_X", "" ) == ""`), it spawns a special player effect entity (`teleport_meditation_cube_playereffect.xml`) at the player's current location.
3.  **State Management**:
    *   It stores the player's return coordinates (`teleport_back_x`, `teleport_back_y`) in global variables. The return Y coordinate is offset by 20 units upwards from the original teleportation point.
    *   `GlobalsSetValue( "TELEPORT_MEDITATION_CUBE_POS_X", tostring( teleport_back_x ) )`
    *   `GlobalsSetValue( "TELEPORT_MEDITATION_CUBE_POS_Y", tostring( teleport_back_y ) )`
4.  **Persistent Flag**:
    *   It adds a persistent flag `secret_meditation` to the game state, likely for tracking progression or enabling specific game elements related to the meditation cube.
    *   `AddFlagPersistent( "secret_meditation" )`