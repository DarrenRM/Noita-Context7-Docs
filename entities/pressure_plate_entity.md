---
title: Pressure Plate Entity
category: entities
---

# Pressure Plate Entity

This document describes the `pressure_plate.xml` entity, a common interactive prop in Noita. It functions as a trigger that activates when a certain amount of material is present on its surface.

## Key Components and Attributes

### `Entity`
The root element for the pressure plate.
- `tags`: "hittable" - Indicates the entity can be interacted with by projectiles or other damaging forces.

### `HitboxComponent`
Defines the physical boundaries of the pressure plate for collision detection.
- `aabb_min_x`, `aabb_max_x`: Defines the horizontal extent of the hitbox.
- `aabb_min_y`, `aabb_max_y`: Defines the vertical extent of the hitbox.

### `VelocityComponent`
Grants the entity velocity, allowing it to be affected by physics.

### `SimplePhysicsComponent`
Applies basic physics to the entity.
- `can_go_up="0"`: Prevents the entity from moving upwards due to physics.

### `SpriteComponent`
Determines the visual representation of the pressure plate.
- `image_file`: Path to the sprite's graphical definition.
- `offset_x`, `offset_y`: Adjusts the sprite's position relative to the entity's origin.

### `PressurePlateComponent`
The core component that defines the pressure plate's behavior.
- `check_every_x_frames`: How often the plate checks for material presence.
- `aabb_min.x`, `aabb_max.x`: Defines the area on the plate where material is checked.
- `aabb_min.y`, `aabb_max.y`: Defines the area on the plate where material is checked.
- `material_percent`: The minimum percentage of material coverage required to activate the plate.

### `LuaComponent`
Allows for custom scripting to extend the pressure plate's functionality.
- `script_pressure_plate_change`: Path to the Lua script that handles the pressure plate's activation and deactivation logic. This script is typically responsible for triggering events or modifying game state when the plate's condition is met.