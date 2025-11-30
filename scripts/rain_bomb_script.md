---
title: Rain Bomb Script
category: scripts
---

# Rain Bomb Script

This script spawns multiple random explosive entities around the player's current location. It attempts to find valid spawn points by performing raycasts to avoid spawning directly into walls.

## Key Attributes

*   **`count`**: The number of explosive entities to spawn.
*   **`types`**: A table of strings representing the names of the explosive entities that can be spawned.
*   **`raycasts`**: The number of raycasts performed to check for valid spawn locations.
*   **`dir`**: The angular separation between raycasts.
*   **`length`**: The length of each raycast.

## Functionality Breakdown

### Initialization

1.  **`dofile_once("data/scripts/lib/utilities.lua")`**: Includes utility functions.
2.  **`GetUpdatedEntityID()`**: Retrieves the ID of the entity executing this script.
3.  **`EntityGetTransform(entity_id)`**: Gets the X and Y coordinates of the entity.
4.  **`SetRandomSeed(...)`**: Initializes the random number generator based on game frame and entity position for deterministic randomness.

### Entity Spawning Loop

The script iterates `count` times to spawn entities.

*   **Random Entity Selection**:
    *   A random index is chosen from the `types` table.
    *   A secondary random multiplier is applied to potentially favor certain types.
*   **Spawn Point Validation**:
    *   A `while` loop attempts to find a suitable spawn location within a 256x256 area around the player.
    *   **Raycasting**: For each potential spawn point, `raycasts` number of rays are cast outwards.
        *   **`RaytraceSurfaces(sx, sy, ex, ey)`**: Checks if a raycast hits a surface (wall).
        *   If any raycast hits a wall, the current spawn point is considered invalid, and a new one is attempted.
    *   **Limit**: A `limit` counter prevents infinite loops if a suitable spot cannot be found after 20 attempts.
*   **Entity Loading**:
    *   If a valid spawn point is found (`failed == false`) and an entity type was successfully selected (`entity ~= nil`):
        *   **`EntityLoad("data/entities/projectiles/" .. entity .. ".xml", pos_x + off_x, pos_y + off_y)`**: Loads the selected explosive entity.
        *   **`EntityLoad("data/scripts/streaming_integration/entities/empty_circle_tiny_bomb.xml", pos_x + off_x, pos_y + off_y)`**: Loads an additional "empty circle tiny bomb" entity at the same location. This might be for visual effects or secondary explosion mechanics.

### Post-Spawn Effect

*   **`GameScreenshake(20)`**: Triggers a screen shake with an intensity of 20 after all entities have been spawned.

## Example Usage (Conceptual)

This script is likely triggered by another entity or game event. For instance, it could be attached to a player's spell or a specific environmental object that activates it.

```lua
-- Example of how this script might be triggered (not part of the script itself)
-- This is a conceptual representation.

-- Assume 'player_entity_id' is the ID of the player
local player_x, player_y = EntityGetTransform(player_entity_id)

-- Create a temporary entity that executes the rain_bomb script
local trigger_entity = EntityLoad("data/entities/trigger_entity.xml", player_x, player_y)
EntityAddComponent(trigger_entity, "LuaComponent", {
    script_path = "data/scripts/streaming_integration/scripts/rain_bomb.lua",
    is_triggered = true -- Assuming a component that allows triggering
})
```

## Potential Modding Extensions

*   **Customizable Entity Types**: Allow modders to easily add or remove entity types from the `types` table.
*   **Spawn Area Control**: Introduce parameters to control the radius or shape of the spawn area.
*   **Spawn Point Filtering**: Add logic to filter spawn points based on biome, surface type, or other environmental factors.
*   **Varying Spawn Counts**: Make the `count` variable dynamic, perhaps based on player stats or game difficulty.
*   **Different Explosion Effects**: Modify the secondary entity loaded to create varied visual or gameplay effects.