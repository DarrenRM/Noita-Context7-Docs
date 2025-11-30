---
title: Gas Pipe Spawner Floor
category: entities
---

# Gas Pipe Spawner Floor

This entity represents a floor tile that periodically spawns gas. It's a building entity primarily controlled by a Lua script.

## Key Components

### LuaComponent

This component dictates the behavior of the gas pipe spawner.

*   **`script_source_file`**: Specifies the Lua script responsible for the entity's logic.
    *   Value: `data/scripts/buildings/gas_pipe_spawn_floor.lua`
*   **`execute_every_n_frame`**: Determines how often the script's logic is executed.
    *   Value: `67` (This means the script will run approximately every 67 frames).