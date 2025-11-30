---
title: Ghostly Ghost Entity
category: entities
---

# Ghostly Ghost Entity

This document describes the `ghostly_ghost.xml` entity, which represents a ghostly, non-physical entity in Noita. It's primarily used for visual effects and unique movement behaviors.

## Core Components

### HitboxComponent
Defines the physical boundaries of the entity.

*   **aabb_min_x**: "-4"
*   **aabb_max_x**: "4"
*   **aabb_min_y**: "-4"
*   **aabb_max_y**: "4"

### SimplePhysicsComponent
Indicates that the entity has basic physics properties.

### VelocityComponent
Manages the entity's movement.

*   **gravity_y**: "0" - This is a key attribute, meaning the entity is not affected by gravity and will float.

### SpriteComponent
Determines the visual appearance of the entity.

*   **image_file**: "data/projectiles_gfx/death_ghost.xml" - Specifies the graphical asset used for the ghost.

### LuaComponent
Attaches custom scripting behavior to the entity.

*   **script_source_file**: "data/scripts/animals/tiny_ghost_move.lua" - Links to a Lua script that controls the ghost's movement logic.
*   **execute_every_n_frame**: "1" - The script runs every frame, allowing for dynamic and responsive movement.