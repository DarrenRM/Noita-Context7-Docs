---
title: Hungry Ghost Perk
category: entities
---

# Hungry Ghost Perk

This entity defines the "Hungry Ghost" perk in Noita. It's a small, ethereal creature that follows the player and consumes nearby projectiles.

## Core Components

### HitboxComponent
Defines the physical boundaries of the ghost.
- `aabb_min_x`, `aabb_max_x`: Horizontal bounds (-4 to 4).
- `aabb_min_y`, `aabb_max_y`: Vertical bounds (-4 to 4).

### SimplePhysicsComponent
Enables basic physics for the entity.

### VelocityComponent
Controls the movement of the ghost.
- `gravity_y`: Set to "0", meaning the ghost is not affected by gravity.

### SpriteComponent
Determines the visual appearance of the ghost.
- `image_file`: Points to the sprite definition (`data/projectiles_gfx/hungry_ghost.xml`).

### LuaComponent (Movement)
Handles the ghost's movement logic.
- `script_source_file`: `data/scripts/animals/tiny_ghost_move.lua`
- `execute_every_n_frame`: "1" (executes every frame).

### LuaComponent (Eating)
Manages the ghost's projectile-eating behavior.
- `_tags`: "hungry_ghost_cooldown" (likely used for internal cooldown management).
- `script_source_file`: `data/scripts/perks/hungry_ghost_eat.lua`
- `execute_every_n_frame`: "1" (executes every frame).

### AudioComponent
Defines the sound effects associated with the ghost.
- `file`: `data/audio/Desktop/animals.bank`
- `event_root`: "animals/tiny_ghost"

### AudioLoopComponent
Manages looping sound effects for the ghost's movement.
- `file`: `data/audio/Desktop/animals.bank`
- `event_name`: "animals/tiny_ghost/movement_loop"
- `set_speed_parameter`: "1" (allows sound speed to be adjusted based on movement).
- `auto_play`: "1" (sound starts automatically).