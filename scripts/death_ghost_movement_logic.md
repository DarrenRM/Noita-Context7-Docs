---
title: Death Ghost Movement Logic
category: scripts
---

# Death Ghost Movement Logic

This script defines the movement behavior for the "Death Ghost" entity in Noita. It causes the ghost to float and bob around its parent entity, with its movement patterns influenced by a global perk count.

## Key Attributes and Behaviors

### Movement Parameters

The script dynamically adjusts several movement parameters based on the `GHOST_PERK_TOTAL_COUNT` global variable. This allows for scaling the ghost's behavior with player progression.

*   **`lerp_amount`**: Controls how smoothly the ghost interpolates towards its target position. A higher value means faster, less smooth movement.
*   **`bob_h`**: The vertical amplitude of the ghost's bobbing motion.
*   **`bob_w`**: The horizontal amplitude of the ghost's bobbing motion.
*   **`bob_speed_y`**: The speed at which the ghost bobs vertically.
*   **`bob_speed_x`**: The speed at which the ghost bobs horizontally.

### Target Acquisition

The ghost's target position is derived from its parent entity's transform.

*   **Parent Entity**: The ghost attempts to follow its parent entity.
*   **Vertical Offset**: The target position is typically set 10 units above the parent's Y-coordinate.

### Randomization

To prevent multiple ghosts from moving identically, the script introduces slight randomization to movement timings and speeds.

*   **Procedural Randomness**: Uses `ProceduralRandomf` with the entity's ID to generate a consistent random value for each ghost.
*   **Time Offset**: Randomizes the `time` variable used for sine wave calculations.
*   **Speed and Lerp Adjustment**: Applies small random variations to `bob_speed_y`, `bob_speed_x`, and `lerp_amount`.

### Bobbing Motion

The ghost exhibits a sine wave-based bobbing motion, creating a floating effect.

*   **Vertical Bob**: `math.sin(time * bob_speed_y) * bob_h`
*   **Horizontal Bob**: `math.sin(time * bob_speed_x) * bob_w`

### Movement Towards Target

The ghost smoothly interpolates its position towards the calculated target.

*   **`vec_lerp`**: A utility function used for linear interpolation between the current and target positions.

### Animation State Management

The script dynamically changes the ghost's sprite animation based on its movement direction and proximity to its target.

*   **Animation Modes**:
    *   `float_`: Used when the ghost is relatively close to its target.
    *   `fly_`: Used when the ghost is further away from its target.
*   **Directional Animations**:
    *   `mode..right`: Applied when the ghost is moving towards the right (positive X direction).
    *   `mode..left`: Applied when the ghost is moving towards the left (negative X direction).
*   **Animation Update Condition**: The animation is only updated if the current animation does not match the required `mode` and direction.

```lua
-- Example of how parameters are calculated based on global perk count
local pickup_count = tonumber( GlobalsGetValue( flag_name, "0" ) )

local bob_h = 6 + pickup_count * 2.5
local bob_w = 20 + pickup_count * 2
local bob_speed_y = 0.065 + 0.0025 * pickup_count
local bob_speed_x = 0.01421 + 0.0025 * pickup_count
```