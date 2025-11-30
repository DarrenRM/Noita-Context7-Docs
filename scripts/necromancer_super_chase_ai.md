---
title: Necromancer Super Chase AI
category: scripts/
---

# Necromancer Super Chase AI

This script defines the AI behavior for a "Necromancer" entity, specifically its "super chase" mode. It dictates how the entity tracks and moves towards the player.

## Key Attributes and Behavior

The AI's behavior is primarily driven by the distance to the player.

### Chase Ranges

*   **`range_near`**: 40 units. If the player is closer than this, the entity stops chasing.
*   **`range_far`**: 250 units. This marks the upper limit for the "near" speed.
*   **`range_max`**: 600 units. If the player is further than this, the entity stops chasing.

### Movement Speeds

*   **`speed_near`**: 0.5. The movement speed used when the player is at `range_near`.
*   **`speed_far`**: 1.0. The movement speed used when the player is at `range_far`.

### Core Logic

1.  **Initialization**:
    *   Retrieves the entity's current ID and transform (position).
    *   Defines a helper function `set_fly_speed` to easily update the entity's flight speed and horizontal velocity multiplier.

2.  **Target Acquisition**:
    *   Searches for the closest entity with the tag "player_unit".
    *   If no player is found, the entity is set to a high default fly speed (40) and the script returns.

3.  **Distance Calculation**:
    *   Calculates the vector and distance between the entity and the player.

4.  **Chase Condition Check**:
    *   If the player is too close (`dist < range_near`) or too far (`dist > range_max`), the entity is set to a high default fly speed (40) and the script returns.

5.  **Movement Towards Player**:
    *   If the player is within the chase range:
        *   The entity's direct flight speed is temporarily set to 0 to allow for precise directional movement.
        *   A movement `speed` is calculated using `map` to interpolate between `speed_near` and `speed_far` based on the current `dist` relative to `range_near` and `range_far`.
        *   The calculated `speed` is clamped to ensure it stays within the defined near and far speeds.
        *   The movement vector is normalized and scaled by the calculated `speed`.
        *   The entity's transform (position) is updated to move it towards the player.

### Helper Functions Used

*   `GetUpdatedEntityID()`: Gets the ID of the entity running the script.
*   `EntityGetTransform(entity_id)`: Gets the position of an entity.
*   `component_write(component, data)`: Writes data to a component.
*   `EntityGetFirstComponent(entity_id, component_name)`: Gets the first instance of a specified component.
*   `EntityGetClosestWithTag(x, y, tag)`: Finds the closest entity with a given tag.
*   `vec_sub(x1, y1, x2, y2)`: Subtracts two vectors.
*   `get_magnitude(vx, vy, x, y)`: Calculates the magnitude of a vector.
*   `map(value, in_min, in_max, out_min, out_max)`: Linearly interpolates a value from one range to another.
*   `clamp(value, min_val, max_val)`: Clamps a value within a specified range.
*   `vec_normalize(vx, vy)`: Normalizes a vector.
*   `vec_mult(vx, vy, scalar)`: Multiplies a vector by a scalar.
*   `vec_add(x1, y1, x2, y2)`: Adds two vectors.
*   `EntitySetTransform(entity_id, x, y)`: Sets the position of an entity.

```lua
-- Example of how speed changes with distance
-- dist = 40  -> speed = 0.5
-- dist = 145 -> speed = 0.75 (midpoint between 40 and 250)
-- dist = 250 -> speed = 1.0
-- dist = 600 -> stops chasing
```