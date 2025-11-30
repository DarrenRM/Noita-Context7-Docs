---
title: Temple Pressure Plate Entity
category: entities
---

# Temple Pressure Plate Entity

This document describes the `temple_pressure_plate.xml` entity, a common interactive prop in Noita. It functions as a pressure plate that triggers events when a certain weight or material is applied to it.

## Key Components

### `HitboxComponent`

Defines the collision area of the pressure plate.

*   `aabb_min_x`: Minimum X-axis bounding box coordinate.
*   `aabb_max_x`: Maximum X-axis bounding box coordinate.
*   `aabb_min_y`: Minimum Y-axis bounding box coordinate.
*   `aabb_max_y`: Maximum Y-axis bounding box coordinate.

### `VelocityComponent`

Indicates that the entity has velocity, though it's typically static in this context.

### `SimplePhysicsComponent`

Manages basic physics properties.

*   `can_go_up`: Set to `0`, meaning the entity cannot move upwards.

### `SpriteComponent`

Determines the visual representation of the pressure plate.

*   `image_file`: Path to the sprite's XML definition.
*   `offset_x`: Horizontal offset for the sprite.
*   `offset_y`: Vertical offset for the sprite.

### `PressurePlateComponent`

The core component that defines the pressure plate's behavior.

*   `check_every_x_frames`: How often the plate's state is checked (in frames).
*   `aabb_min.x`, `aabb_max.x`, `aabb_min.y`, `aabb_max.y`: Defines the active area for pressure detection.
*   `material_percent`: The percentage of the area that needs to be covered by material to trigger the plate.

### `LuaComponent`

Links the entity to a Lua script for custom behavior.

*   `script_pressure_plate_change`: Path to the Lua script that handles the pressure plate's logic when activated or deactivated.

## Lua Scripting

The `LuaComponent` points to `data/scripts/props/temple_pressure_plate.lua`. This script is responsible for defining what happens when the pressure plate is activated (e.g., by a player, enemy, or falling object) or deactivated. This could involve opening doors, activating traps, or triggering other game events.