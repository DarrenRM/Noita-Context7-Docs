---
title: Barren Puzzle Logic - Success State
category: biome
---

# Barren Puzzle Logic - Success State

This Lua script defines the behavior when a specific puzzle in the Barren biome is successfully completed. It handles visual effects, sound cues, item creation, and biome modification.

## Key Functions

### `material_area_checker_success( pos_x, pos_y )`

This function is triggered upon successful completion of the puzzle.

*   **`pos_x`, `pos_y`**: The coordinates where the success event occurred.

#### Core Actions:

1.  **Visual Effect**: Spawns a "magical_symbol" particle effect at a slightly offset position (`sx`, `y`).
2.  **Sound Cues**:
    *   Plays a "crumbling\_earth/create" sound.
    *   Plays an "event\_cues/barren\_puzzle\_completed/create" sound.
3.  **Item Creation**: Creates an entity with the "CESSATION" action at the specified location.
4.  **Persistent Flag**: Adds a persistent flag `card_unlocked_cessation` to the game state, likely indicating that a related card has been unlocked.
5.  **Biome Material Conversion**:
    *   Defines source material `templeslab_static` and target material `grass_holy`.
    *   Converts a rectangular area of `templeslab_static` to `grass_holy` instantly. The area is defined by `xmin`, `xmax`, and a fixed height.

#### Key Parameters for Material Conversion:

*   **`mat_from`**: `CellFactory_GetType( "templeslab_static" )` - The material to be replaced.
*   **`mat_to`**: `CellFactory_GetType( "grass_holy" )` - The material to replace with.
*   **`xmin`, `xmax`**: `330`, `300` - Define the horizontal extent of the conversion area relative to the puzzle's center.
*   **`y`**: The vertical position of the puzzle.
*   **`52`**: The height of the conversion area.
*   **`true`**: Indicates that the conversion should be instant.
*   **`false`**: Likely related to whether the conversion should be animated or not.

---

**Note:** This script is intended to be called by an entity that acts as a trigger for the puzzle's success condition. The specific entity that calls this function is not detailed in this snippet.