---
title: Angry Ghost Perk Entity
category: entities
---

# Angry Ghost Perk Entity

This entity defines the "Angry Ghost" perk in Noita. It's a passive perk that grants the player a spectral companion that mimics their projectile choices.

## Key Components

### HitboxComponent
Defines the physical boundaries of the angry ghost.

*   **aabb_min_x**: -4
*   **aabb_max_x**: 4
*   **aabb_min_y**: -3
*   **aabb_max_y**: 3

### SimplePhysicsComponent
Enables basic physics for the entity.

### VelocityComponent
Controls the movement of the entity.

*   **gravity_y**: 0 (The ghost does not experience gravity.)

### SpriteComponent
Determines the visual appearance of the angry ghost.

*   **image\_file**: `data/projectiles_gfx/angry_ghost.xml`

### LuaComponent (Movement)
Handles the ghost's movement logic.

*   **script\_source\_file**: `data/scripts/animals/tiny_ghost_move.lua`
*   **execute\_every\_n\_frame**: 1

### LuaComponent (Memory)
Manages the ghost's ability to remember and replicate projectile spells.

*   **script\_source\_file**: `data/scripts/perks/angry_ghost_memory.lua`
*   **execute\_every\_n\_frame**: 1

### VariableStorageComponent (Cooldown)
Stores a cooldown timer for the ghost's actions.

*   **name**: `cooldown`
*   **value\_int**: 0

### VariableStorageComponent (Projectile Memory)
Stores the projectile entity that the ghost will mimic.

*   **name**: `projectile_memory`
*   **value\_string**: `data/entities/projectiles/deck/light_bullet.xml` (Default projectile to mimic)

### AudioComponent
Manages the sound effects associated with the angry ghost.

*   **file**: `data/audio/Desktop/animals.bank`
*   **event\_root**: `animals/tiny_ghost`

### AudioLoopComponent
Handles the looping ambient sound of the angry ghost.

*   **file**: `data/audio/Desktop/animals.bank`
*   **event\_name**: `animals/tiny_ghost/movement_loop`
*   **set\_speed\_parameter**: 1
*   **auto\_play**: 1