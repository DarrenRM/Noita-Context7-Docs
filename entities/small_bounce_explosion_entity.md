---
title: Small Bounce Explosion Entity
category: entities
---

# Small Bounce Explosion Entity

This entity defines a small explosion effect that bounces. It's primarily controlled by a Lua script.

## Key Components

### LuaComponent
This component links the entity to its behavior defined in a Lua script.

*   **`script_source_file`**: `data/scripts/projectiles/bounce_small_explosion.lua`
    *   This specifies the Lua script that governs the entity's behavior, including its explosion and bouncing mechanics.
*   **`execute_every_n_frame`**: `1`
    *   The script logic will be executed every frame.
*   **`remove_after_executed`**: `1`
    *   The entity will be removed from the game world after the script has executed its primary logic.

## Usage

This entity is likely used as a projectile or a particle effect that, upon impact or after a certain duration, triggers a small explosion and then continues to bounce. The specific visual and functional aspects of the explosion and bouncing are handled within the `bounce_small_explosion.lua` script.