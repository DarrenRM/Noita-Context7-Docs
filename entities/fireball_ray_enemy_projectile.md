---
title: Fireball Ray Enemy Projectile
category: entities
---

# Fireball Ray Enemy Projectile

This entity defines the behavior and properties of a fireball ray projectile used by enemies in Noita.

## Core Components

### LuaComponent
This component links the entity to a Lua script that governs its specific actions and logic.

*   **script\_source\_file**: `data/scripts/projectiles/fireball_ray_enemy.lua` - The primary script controlling the projectile's behavior.
*   **execute\_every\_n\_frame**: `10` - The script will execute its logic every 10 frames.

### LifetimeComponent
This component determines how long the projectile will exist before despawning.

*   **lifetime**: `5000` - The projectile will last for 5000 frames (approximately 83 seconds).

### InheritTransformComponent
This component indicates that the entity inherits transformation properties (like position, rotation, scale) from its parent or creator. This is common for projectiles spawned by other entities.