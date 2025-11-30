---
title: Pipe Bomb Detonator Projectile
category: entities
---

# Pipe Bomb Detonator Projectile

This entity defines the behavior of the "Pipe Bomb Detonator" projectile in Noita. It primarily utilizes a Lua script to manage its functionality.

## Key Components

### LuaComponent

This component is responsible for executing the projectile's logic.

*   **`_enabled`**: `1` (Component is active)
*   **`execute_on_added`**: `1` (The script will execute immediately when the projectile is added to the game)
*   **`remove_after_executed`**: `1` (The projectile entity will be removed after the script finishes execution)
*   **`script_source_file`**: `data/scripts/projectiles/pipe_bomb_detonator.lua` (Specifies the Lua script file that controls the projectile's behavior)