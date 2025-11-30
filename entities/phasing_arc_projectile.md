---
title: Phasing Arc Projectile
category: entities
---

# Phasing Arc Projectile

This entity defines the behavior of the "Phasing Arc" projectile in Noita. It primarily relies on a Lua script for its functionality.

## Key Components

### LuaComponent

This component links the entity to its associated Lua script, which dictates its in-game behavior.

*   **`script_source_file`**: `data/scripts/projectiles/phasing_arc.lua`
    *   This specifies the path to the Lua script that controls the projectile's logic.
*   **`execute_every_n_frame`**: `12`
    *   The script logic will be executed every 12 frames, controlling the projectile's update rate.

## Summary

The `phasing_arc.xml` file is a minimal entity definition. Its core functionality is entirely managed by the `phasing_arc.lua` script, which is responsible for how the projectile moves, interacts, and its visual effects. The `execute_every_n_frame` attribute suggests a periodic update mechanism for the projectile's behavior.