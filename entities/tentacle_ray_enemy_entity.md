---
title: Tentacle Ray Enemy Entity
category: entities
---

# Tentacle Ray Enemy Entity

This document describes the `tentacle_ray_enemy.xml` entity, which defines a basic enemy that utilizes a tentacle ray attack.

## Key Components

### LuaComponent
This component is responsible for the entity's behavior, executing a Lua script to manage its actions.

*   **`script_source_file`**: `data/scripts/projectiles/tentacle_ray_enemy.lua` - Specifies the Lua script that controls the entity's logic.
*   **`execute_every_n_frame`**: `10` - The script will be executed every 10 frames.

### LifetimeComponent
This component defines how long the entity will exist.

*   **`lifetime`**: `5000` - The entity will persist for 5000 frames.

### InheritTransformComponent
This component indicates that the entity inherits transformation properties (like position, rotation, scale) from its parent or the environment.