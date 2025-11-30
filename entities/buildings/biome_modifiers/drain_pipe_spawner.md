---
title: Drain Pipe Spawner
category: entities/buildings/biome_modifiers
---

# Drain Pipe Spawner

This entity is responsible for spawning drain pipes within the game world. It utilizes a Lua script to manage the spawning process.

## Key Components

### LuaComponent

This component dictates the behavior of the drain pipe spawner through a Lua script.

*   **`script_source_file`**: Specifies the path to the Lua script that controls the spawner's logic.
    *   Value: `data/scripts/buildings/drain_pipe_spawn.lua`
*   **`execute_every_n_frame`**: Determines how frequently the script's logic is executed.
    *   Value: `67` (The script will run approximately every 67 frames).