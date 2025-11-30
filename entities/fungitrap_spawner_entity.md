---
title: Fungitrap Spawner Entity
category: entities
---

# Fungitrap Spawner Entity

This entity is responsible for spawning fungi within the game world, likely as part of a "fungitrap" mechanism. It primarily relies on a Lua script to manage its behavior.

## Core Components

### LuaComponent

This is the primary component that dictates the entity's functionality.

*   **`script_source_file`**: `data/scripts/buildings/fungitrap_02_spawner.lua`
    *   This attribute points to the Lua script that controls the spawner's logic, including how and when fungi are generated.
*   **`execute_every_n_frame`**: `1`
    *   Indicates that the associated Lua script will be executed every single frame, suggesting a continuous or highly frequent update cycle for the spawner.

## Summary

The `fungitrap_02_spawner.xml` file defines an entity that acts as a spawner for fungi. Its behavior is entirely driven by the `fungitrap_02_spawner.lua` script, which is executed every frame. This setup implies that the spawner actively monitors conditions and generates fungi based on the logic defined in its associated Lua file.