---
title: Desert Ruins Spawner
category: entities
---

# Desert Ruins Spawner

This entity is responsible for spawning elements within the desert ruins biome. It utilizes a Lua script to manage its spawning behavior.

## LuaComponent

This component defines the script that controls the entity's functionality.

### Key Attributes:

*   **`script_source_file`**: Specifies the path to the Lua script file.
    *   `data/scripts/props/overworld_desert_ruins_spawner.lua`
*   **`execute_on_added`**: When set to `1`, the script will execute immediately after the entity is added to the game world.
*   **`execute_every_n_frame`**: When set to `-1`, the script will only execute once (due to `execute_on_added`). If set to a positive integer, it would execute every N frames.