---
title: Spatial Map Perk Logic
category: scripts
---

---

# Spatial Map Perk Logic

This script defines the behavior for the "Spatial Map" perk in Noita, which reveals parts of the map and player/friend locations when the player stands still.

## Key Functionality

The script primarily focuses on:

*   **Tracking Player Movement:** It detects if the player is actively moving or standing still.
*   **Map Revelation:** When the player is stationary, it gradually reveals parts of the map by spawning sprites.
*   **Player and Friend Location Markers:** It displays sprites indicating the player's current position and the positions of any allies.
*   **Parallel World Indicator:** It can display an indicator for the parallel world the player is in.

## Core Attributes and Logic

### Player State Detection

*   **`entity_id`**: The unique identifier for the entity running this script (likely a perk entity).
*   **`player_id`**: The root entity ID of the player.
*   **`x`, `y`**: Player's current coordinates.
*   **`pw`, `mx`**: Variables related to parallel world and player's X-coordinate within the map.
*   **`is_moving`**: A boolean flag that becomes `true` if any movement or action input is detected from the player.

### Map Revelation Timer and Stages

*   **`timer`**: An integer that increments when the player is stationary.
*   **`timercomp`**: A reference to the `VariableStorageComponent` holding the `map_timer` value.
*   **Revelation Stages**: The `timer` value dictates which map sprite is displayed, creating a visual progression:
    *   `timer > 80`: Base map revelation begins.
    *   `timer > 82`: `spatial_map_2` sprite.
    *   `timer > 84`: `spatial_map_3` sprite.
    *   `timer > 86`: `spatial_map_4` sprite.

### Sprite Generation and Positioning

*   **`map_sprite`**: The name of the sprite to be spawned for map revelation.
*   **`map_x`, `map_y`**: Base coordinates for map revelation.
*   **`mult_x`, `mult_y`**: Scaling factors for translating map coordinates to screen space.
*   **`dx`, `dy`**: Calculated offsets to position the map revelation sprites relative to the player.
*   **`mi_x`, `mi_y`**: Coordinates for the "map indicator" sprite.
*   **`pi_x`, `pi_y`**: Coordinates for the "player indicator" sprite.
*   **`GameCreateSpriteForXFrames()`**: The primary function used to spawn visual elements.

### Special Indicators

*   **Friend Location (`spatial_map_friend.png`)**:
    *   Spawned at `mi_x + fx`, `mi_y + fy`.
    *   `fx`, `fy` are derived from a random selection of predefined "friend spots" (`fspots`).
*   **Parallel World Indicator (`spatial_map_pw_X.png`)**:
    *   Spawned at `mi_x + 6`, `mi_y - 92`.
    *   The sprite name dynamically changes based on the `pw` value (e.g., `spatial_map_pw_1`, `spatial_map_pw_m2`).

### Reset Condition

*   If `is_moving` is `true` (player is actively doing something), the `timer` is reset to `0`.