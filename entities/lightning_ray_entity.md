---
title: Lightning Ray Entity
category: entities
---

# Lightning Ray Entity

This entity defines the behavior of a lightning ray projectile in Noita.

## Core Components

### LuaComponent
This component is responsible for the dynamic behavior of the lightning ray.

*   **`script_source_file`**: `data/scripts/projectiles/lightning_ray.lua` - Specifies the Lua script that controls the ray's logic.
*   **`execute_every_n_frame`**: `10` - The script will be executed every 10 frames, controlling the ray's animation and effects.

## Key Attributes

The `lightning_ray.xml` file is very minimal, primarily serving as a container for the `LuaComponent` that drives the projectile's functionality. The actual visual and behavioral aspects are handled within the associated Lua script.