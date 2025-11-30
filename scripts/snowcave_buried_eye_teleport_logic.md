---
title: Snowcave Buried Eye Teleport Logic
category: scripts
---

# Snowcave Buried Eye Teleport Logic

This script defines the behavior for a teleportation mechanism associated with the "Buried Eye" in the Snowcave biome. When a player uses this teleport, it records their departure position and sets persistent flags.

## Key Functionality

### `portal_teleport_used( entity_teleported, from_x, from_y, to_x, to_y )`

This function is triggered when an entity is teleported.

*   **`entity_teleported`**: The entity that was teleported.
*   **`from_x`, `from_y`**: The coordinates from which the entity was teleported.
*   **`to_x`, `to_y`**: The coordinates to which the entity was teleported.

### Player Teleportation Logic

When the `entity_teleported` is a player:

1.  **Teleport Back Position Calculation**:
    *   Calculates a `teleport_back_x` by subtracting 50 units from the `from_x` coordinate.
    *   The `teleport_back_y` remains the same as `from_y`.

2.  **Global Variable Storage**:
    *   Stores the calculated `teleport_back_x` in the global variable `TELEPORT_SNOWCAVE_BURIED_EYE_POS_X`.
    *   Stores the calculated `teleport_back_y` in the global variable `TELEPORT_SNOWCAVE_BURIED_EYE_POS_Y`.
    *   These global variables are converted to strings using `tostring()`.

3.  **Persistent Flag**:
    *   Adds a persistent flag named `"secret_buried_eye"` using `AddFlagPersistent()`. This flag is likely used to track progression or unlock content related to this teleport.

## Global Variables Modified

*   `TELEPORT_SNOWCAVE_BURIED_EYE_POS_X` (string): Stores the X-coordinate for a potential "teleport back" location.
*   `TELEPORT_SNOWCAVE_BURIED_EYE_POS_Y` (string): Stores the Y-coordinate for a potential "teleport back" location.

## Persistent Flags Added

*   `secret_buried_eye`: A flag indicating that the "secret buried eye" mechanism has been activated or used.