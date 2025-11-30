---
title: Gas Pipe Spawner
category: entities/buildings/biome_modifiers
---

# Gas Pipe Spawner

This entity is responsible for spawning gas pipes within biomes. It utilizes a Lua script to manage the spawning process.

## Key Components

### LuaComponent

This component dictates the behavior of the gas pipe spawner.

| Attribute         | Description                                                                 |
| :---------------- | :-------------------------------------------------------------------------- |
| `script_source_file` | Specifies the Lua script file that controls the spawning logic.             |
| `execute_every_n_frame` | Determines how often the script's logic is executed (in frames). A value of 67 means it runs approximately every 1.1 seconds (60 frames per second). |

## Lua Script (`data/scripts/buildings/gas_pipe_spawn.lua`)

The `gas_pipe_spawn.lua` script contains the core logic for how and where gas pipes are generated. While the full script is not provided here, it would typically handle:

*   **Biome Detection:** Identifying which biome the spawner is currently in.
*   **Spawn Conditions:** Determining if conditions are met for spawning a gas pipe (e.g., based on biome type, player proximity, or other game state variables).
*   **Gas Pipe Entity Instantiation:** Creating new gas pipe entities in the game world.
*   **Placement Logic:** Deciding the position and orientation of the spawned gas pipes.

**Note:** For detailed information on the spawning logic, refer to the `data/scripts/buildings/gas_pipe_spawn.lua` file.