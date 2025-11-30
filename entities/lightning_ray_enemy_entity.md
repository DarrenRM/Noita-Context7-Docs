---
title: Lightning Ray Enemy Entity
category: entities
---

# Lightning Ray Enemy Entity

This entity defines the behavior and properties of a lightning ray enemy in Noita.

## Key Components

### LuaComponent
This component is responsible for the entity's dynamic behavior, executing a Lua script.

*   **script\_source\_file**: `data/scripts/projectiles/lightning_ray_enemy.lua` - Specifies the Lua script that controls the lightning ray's actions.
*   **execute\_every\_n\_frame**: `10` - The script will be executed every 10 frames.

### LifetimeComponent
This component determines how long the entity will exist.

*   **lifetime**: `5000` - The lightning ray will exist for 5000 frames.

### InheritTransformComponent
This component indicates that the entity inherits transformation properties (like position, rotation, scale) from its parent or creator. This is a common component for entities that are spawned dynamically.