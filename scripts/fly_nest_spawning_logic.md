---
title: Fly Nest Spawning Logic
category: scripts
---

# Fly Nest Spawning Logic

This script defines the behavior for a "Fly Nest" entity in Noita, specifically its logic for spawning flies.

## Core Functionality

The primary purpose of this script is to periodically spawn "fly" entities near the nest, but only under certain conditions.

## Key Attributes & Logic

*   **`entity_id`**: Retrieves the unique identifier for the current nest entity.
*   **`pos_x`, `pos_y`**: Gets the current world coordinates of the nest.
*   **Random Seed Initialization**: `SetRandomSeed` is used to ensure pseudo-randomness based on game frame and entity position, influencing spawn chances and fly placement.
*   **Spawn Chance**: There's a 75% chance for the script to attempt spawning a fly on any given frame.
*   **Player Proximity Check**:
    *   The script searches for the closest player entity (`"player_unit"`).
    *   If a player is found, it calculates the distance between the player and the nest.
    *   Spawning only occurs if the player is within a `spawn_distance` of 200 units.
*   **Spawn Limit**: The nest will only spawn flies if the current count of spawned flies (tracked by the `"spawned"` value) is less than 15.
*   **Fly Entity Loading**:
    *   If all conditions are met, a new fly entity is loaded from `data/entities/animals/fly.xml`.
    *   The fly is spawned slightly offset from the nest's position (`pos_x - 3`, `pos_y - 4`).
*   **Fly Script Modification**: A Lua component on the spawned fly is edited to set its `script_death` to an empty string, potentially altering its death behavior.
*   **Increment Spawn Count**: The `spawned_entities` counter is incremented, and this value is updated for the nest entity.

## Example Usage (Conceptual)

This script would be attached to an entity defined in an XML file, likely within the `data/entities/buildings/` directory. The XML would reference this Lua script via a `LuaComponent`.

```lua
-- Example XML snippet (not part of the provided Lua, but for context)
<entity name="fly_nest">
    <LuaComponent
        script_path="data/scripts/buildings/flynest.lua"
        run_every_frame="true" />
    <... other components ...>
</entity>
```