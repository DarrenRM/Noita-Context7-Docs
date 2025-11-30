---
title: Larpa Death Entity
category: entities
---

# Larpa Death Entity

This entity is designed to trigger a specific Lua script when it is removed. It's a simple entity primarily used for its `LuaComponent`.

## Key Components

### LuaComponent

This component is responsible for executing Lua code.

*   **`script_source_file`**: `data/scripts/projectiles/larpa_death.lua`
    *   This specifies the Lua script that will be executed.
*   **`execute_every_n_frame`**: `-1`
    *   Indicates that the script is not executed on a regular frame interval.
*   **`execute_on_removed`**: `1`
    *   This is the crucial setting. The associated Lua script will be executed *only* when this entity is removed from the game world.

## Usage

This entity acts as a trigger. When the conditions for its removal are met (e.g., it's destroyed, despawned, or otherwise removed), the `larpa_death.lua` script will run. This is commonly used for effects that should occur upon the "death" or disappearance of a specific projectile or entity.