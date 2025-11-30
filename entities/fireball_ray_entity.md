---
title: Fireball Ray Entity
category: entities
---

# Fireball Ray Entity

This document describes the `fireball_ray.xml` entity, which is likely used to define the behavior and properties of a "fireball ray" projectile within Noita.

## Core Components

### LuaComponent

This component is responsible for executing custom Lua script logic for the entity.

*   **`script_source_file`**: `data/scripts/streaming_integration/scripts/fireball_ray.lua` - Specifies the Lua script file that controls the entity's behavior.
*   **`execute_every_n_frame`**: `20` - The script will be executed every 20 frames.

### LifetimeComponent

This component defines how long the entity will exist before being removed.

*   **`lifetime`**: `300` - The entity will persist for 300 frames.

### InheritTransformComponent

This component indicates that the entity inherits transformation properties (like position, rotation, scale) from its parent or the context in which it is spawned. This is a common component for projectiles and other spawned entities.