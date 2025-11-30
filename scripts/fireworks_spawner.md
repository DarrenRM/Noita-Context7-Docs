---
title: Fireworks Spawner
category: scripts
---

# Fireworks Spawner

This script spawns a configurable number of "physics_pata.xml" entities at random locations near the spawner, ensuring they are not too close to walls.

## Key Attributes

*   **`count`**: The number of entities to spawn.
*   **`raycasts`**: The number of raycasts used to check for walls around potential spawn points.
*   **`dir`**: The angular separation between raycasts.
*   **`length`**: The length of each raycast.
*   **`limit`**: A safety counter to prevent infinite loops if suitable spawn points cannot be found.
*   **`off_x`, `off_y`**: Random offsets from the spawner's position to determine the spawn point.
*   **`wall`**: A boolean flag indicating if a raycast hit a surface.
*   **`failed`**: A boolean flag indicating if the script failed to find a suitable spawn point after multiple attempts.

## Functionality

1.  **Initialization**:
    *   Gets the spawner entity's ID and position.
    *   Sets a random seed based on game frame and position for varied results.
    *   Initializes spawn parameters like `count`, `raycasts`, `dir`, and `length`.

2.  **Spawn Loop**:
    *   Iterates `count` times to spawn entities.
    *   Inside the loop, it attempts to find a valid spawn location:
        *   Generates random `off_x` and `off_y` offsets.
        *   Performs `raycasts` in different directions from the potential spawn point.
        *   Checks if any raycast hits a surface (`wall`).
        *   If a wall is detected or the `limit` is reached, it retries or marks the spawn as `failed`.

3.  **Entity Spawning**:
    *   If a suitable spawn point is found (`failed` is false), it loads the `data/entities/props/physics_pata.xml` entity at the calculated position.

4.  **Screen Shake**:
    *   Applies a screen shake effect after the spawning process.

## Example Usage (Conceptual)

This script is typically attached to an entity that should trigger the fireworks effect. The `count` attribute can be adjusted to control the density of the fireworks.

```lua
-- Example of how this script might be integrated into another entity's XML:
-- <Entity tags="script_entity">
--     <LuaComponent
--         script_path="data/scripts/streaming_integration/scripts/fireworks.lua"
--         execute_every_frame="false"
--         remove_after_executed="true"
--     />
-- </Entity>
```