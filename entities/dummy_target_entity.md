---
title: Dummy Target Entity
category: entities
---

# Dummy Target Entity

This entity represents a simple, stationary target that can be hit and damaged. It's primarily used for testing or as a basic prop in the game world.

## Key Components

### `Entity`
The root element for the entity.

*   **`tags`**: `prop`, `hittable`, `mortal`, `homing_target` - These tags define its behavior and how it interacts with other game systems.

### `VelocityComponent`
Indicates that the entity has velocity properties, though it's typically stationary by default.

### `SimplePhysicsComponent`
Enables basic physics interactions for the entity.

### `SpriteComponent`
Defines the visual representation of the entity.

*   **`z_index`**: `1` - Controls the rendering order.
*   **`image_file`**: `data/props_gfx/dummy_target.xml` - Specifies the graphical asset used for the sprite.
*   **`offset_x`**, **`offset_y`**: `0` - No offset from the entity's origin.

### `DamageModelComponent`
Manages how the entity takes damage and its health.

*   **`hp`**: `120` - The entity's health points.
*   **`blood_material`**: `sand` - The material that is produced when the entity is damaged.
*   **`blood_multiplier`**: `0.01` - Controls the amount of blood material generated.
*   **`air_needed`**: `0` - Does not require air to function.
*   **`falling_damages`**: `0` - Does not take damage from falling.
*   **`fire_damage_amount`**, **`fire_probability_of_ignition`**: `0` - Immune to fire damage.
*   **`critical_damage_resistance`**: `0` - No resistance to critical damage.
*   **`drop_items_on_death`**: `0` - Does not drop items upon death.
*   **`is_on_fire`**: `0` - Starts with no fire effect.
*   **`materials_create_messages`**, **`materials_damage`**: `0` - Does not interact with materials in these ways.
*   **`ragdoll_filenames_file`**, **`ragdoll_material`**: `""` - No ragdoll physics are applied on death.

### `HitboxComponent`
Defines the collision area of the entity.

*   **`aabb_min_x`**: `-8.5`
*   **`aabb_max_x`**: `8.5`
*   **`aabb_min_y`**: `-22`
*   **`aabb_max_y`**: `0`
    These values define an axis-aligned bounding box (AABB) for the entity's hitbox.