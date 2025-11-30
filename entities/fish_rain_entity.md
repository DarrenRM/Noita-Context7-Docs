---
title: Fish Rain Entity
category: entities
---

# Fish Rain Entity

This entity defines the behavior for a "fish rain" effect in Noita. It primarily uses Lua scripts to manage the spawning and behavior of fish.

## Key Components

### LifetimeComponent

*   **lifetime**: `300` - The duration in frames this entity will exist.
*   **serialize\_duration**: `1` - How long the entity's state should be serialized.

### LuaComponent (Primary Spawning)

*   **\_enabled**: `1` - Indicates the component is active.
*   **execute\_every\_n\_frame**: `20` - The script will execute every 20 frames.
*   **script\_source\_file**: `data/scripts/buildings/spawn_fish_rain.lua` - This is the main script responsible for spawning the fish rain effect.

### LuaComponent (Cleanup/Secondary)

*   **\_enabled**: `1` - Indicates the component is active.
*   **execute\_on\_removed**: `1` - The script will execute when this entity is removed.
*   **execute\_every\_n\_frame**: `-1` - This likely means it doesn't execute on a frame interval, but rather on the `execute_on_removed` trigger.
*   **script\_source\_file**: `data/scripts/buildings/spawn_leukaluu.lua` - This script might be for a specific type of fish or a cleanup routine related to the fish rain.

## Summary

The `fish_rain.xml` entity is a simple container that leverages Lua scripting to create a dynamic "fish rain" effect. The primary `LuaComponent` triggers a script every 20 frames to manage the spawning, while a secondary `LuaComponent` handles actions upon the entity's removal. The `LifetimeComponent` dictates how long the entity, and thus the fish rain effect, persists.