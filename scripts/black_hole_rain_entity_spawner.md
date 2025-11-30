---
title: Black Hole Rain Entity Spawner
category: scripts
---

# Black Hole Rain Entity Spawner

This script is responsible for spawning "black hole" entities in a rain-like pattern around the player's current position.

## Core Functionality

*   **Entity Spawning:** Creates instances of `data/entities/projectiles/deck/black_hole_big.xml`.
*   **Randomized Placement:** Spawns entities within a defined radius around the player.
*   **Screen Shake:** Triggers a screen shake effect upon execution.

## Key Attributes

### Spawning Logic

*   **`count`**: Determines the number of black holes to spawn. Currently set to `1`.
*   **Placement Loop**:
    *   Iterates to find suitable spawn locations.
    *   Uses `Random(-216, 216)` and `Random(-166, 166)` to generate random offsets (`off_x`, `off_y`) from the player's position.
    *   **Placement Constraint**: Ensures the absolute sum of offsets (`math.abs(off_x) + math.abs(off_y)`) is greater than `90` to avoid spawning too close to the player.
    *   **Limit**: Includes a `limit` to prevent infinite loops if suitable spots cannot be found after 20 attempts.
*   **`EntityLoad()`**: Loads the specified black hole entity at the calculated position.

### Visual/Audio Effects

*   **`GameScreenshake(20)`**: Applies a screen shake with an intensity of `20`.

## Example Usage (within Noita)

This script is typically triggered by an in-game event or entity that initiates the "black hole rain" effect. The `entity_id` is dynamically retrieved, implying it's attached to an entity that is active in the game world.

```lua
-- Example of how the script might be called (conceptual)
-- This is not part of the script itself, but shows its context.

-- Assume 'some_trigger_entity' is an entity in the game world
-- and it has this script attached to it.

-- When 'some_trigger_entity' is activated:
-- The script will run, get its own entity_id, and proceed to spawn black holes.
```