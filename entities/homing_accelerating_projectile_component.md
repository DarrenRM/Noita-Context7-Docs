---
title: Homing Accelerating Projectile Component
category: entities
---

# Homing Accelerating Projectile Component

This entity defines a projectile with homing and accelerating behavior.

## Key Components

### HomingComponent
This component enables the projectile to actively seek out targets.

*   **`homing_targeting_coeff`**: Controls how strongly the projectile targets its destination. Higher values mean more aggressive turning.
*   **`homing_velocity_multiplier`**: Adjusts the projectile's speed when homing.
*   **`detect_distance`**: The maximum distance at which the projectile can detect and target enemies.

### LuaComponent
This component links the entity to a Lua script for custom behavior.

*   **`script_source_file`**: Specifies the Lua script responsible for the projectile's logic. In this case, it's `data/scripts/projectiles/homing_accelerating.lua`.
*   **`execute_every_n_frame`**: Determines how frequently the Lua script is executed. `1` means it runs every frame.

## Example Usage

This entity is typically used as a base for projectiles that need to pursue enemies and increase their speed over time, as dictated by the associated Lua script.