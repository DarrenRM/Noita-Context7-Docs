---
title: Desert Prop Spawner Entity
category: entities
---

# Desert Prop Spawner Entity

This entity is responsible for spawning various props within the desert biome. It utilizes a Lua script to manage the spawning logic.

## Key Components

### LuaComponent
This component defines the script that controls the entity's behavior.

*   **`script_source_file`**: `data/scripts/props/overworld_desert_prop_spawner.lua`
    *   This is the path to the Lua script that handles the spawning of desert props.
*   **`execute_on_added`**: `1`
    *   Indicates that the script should execute immediately when the entity is added to the game world.
*   **`execute_every_n_frame`**: `-1`
    *   This value suggests that the script is not intended to run repeatedly on a frame-by-frame basis after its initial execution. It likely performs its spawning tasks once upon activation.

## Functionality

The `overworld_desert_prop_spawner.lua` script (referenced by the `LuaComponent`) is the core of this entity's functionality. While the XML only defines the entity and its script linkage, the Lua script would contain the specific logic for:

*   Determining *which* desert props to spawn.
*   Defining the *locations* and *density* of these spawns.
*   Potentially handling *conditions* for spawning (e.g., based on biome type, player proximity, or game state).

To understand the exact props spawned and their behavior, one would need to examine the `data/scripts/props/overworld_desert_prop_spawner.lua` file.