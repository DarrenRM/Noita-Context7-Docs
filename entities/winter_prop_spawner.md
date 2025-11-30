---
title: Winter Prop Spawner
category: entities
---

# Winter Prop Spawner

This entity is responsible for spawning environmental props in the winter biome.

## LuaComponent

This component links the entity to its associated Lua script, which handles the spawning logic.

### Key Attributes:

*   **`script_source_file`**: Specifies the path to the Lua script that controls the spawning behavior.
    *   Value: `data/scripts/props/overworld_winter_prop_spawner.lua`
*   **`execute_on_added`**: Determines if the script should execute immediately when the entity is added to the game world.
    *   Value: `1` (True)
*   **`execute_every_n_frame`**: Controls how often the script is executed. A value of `-1` typically means it runs only once or is controlled by other script logic.
    *   Value: `-1`