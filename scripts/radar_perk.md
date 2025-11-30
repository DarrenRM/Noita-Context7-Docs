---
title: Radar Perk
category: scripts
---

---

# Radar Perk

This script implements the functionality for the "Radar" perk in Noita. It pings nearby enemies, displaying visual indicators around the player based on their proximity.

## Key Functionality

### Enemy Detection

*   **Range:** Enemies within a `range` of 400 units are detected.
*   **Tagging:** Detection relies on entities having the `"enemy"` tag.
*   **Positioning:** The script retrieves the player's position (`pos_x`, `pos_y`) and offsets it slightly for accurate detection.

### Indicator Display

*   **Proximity-Based Sprites:** Different sprites are used to indicate enemy proximity:
    *   `data/particles/radar_enemy_strong.png`: For enemies within 50% of the detection range.
    *   `data/particles/radar_enemy_medium.png`: For enemies between 50% and 80% of the detection range.
    *   `data/particles/radar_enemy_faint.png`: For enemies beyond 80% of the detection range.
*   **Indicator Placement:**
    *   If an enemy is within the camera bounds, the indicator is placed directly above the enemy.
    *   If an enemy is outside the camera bounds, the indicator is positioned around the player at a fixed `indicator_distance` of 40 units, in the direction of the enemy.

### Sprite Creation

*   **`GameCreateSpriteForXFrames`:** This function is used to create the visual indicators.
    *   `true` for the `is_world_entity` parameter indicates that the sprite is part of the game world.
    *   `0, 0, 1` for rotation and scale parameters.
    *   The final `true` parameter enables sprite rendering.

## Key Attributes

| Attribute           | Description                                                                                             |
| :------------------ | :------------------------------------------------------------------------------------------------------ |
| `range`             | The maximum distance at which enemies are detected.                                                       |
| `indicator_distance`| The fixed distance from the player where indicators are placed for off-screen enemies.                    |
| `"enemy"`           | The tag used to identify entities that should be considered enemies for radar detection.                  |
| `radar_enemy_strong.png` | Sprite used for close enemies.                                                                          |
| `radar_enemy_medium.png` | Sprite used for medium-range enemies.                                                                   |
| `radar_enemy_faint.png`  | Sprite used for distant enemies.                                                                        |