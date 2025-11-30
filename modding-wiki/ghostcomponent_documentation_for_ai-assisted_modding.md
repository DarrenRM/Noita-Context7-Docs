---
title: GhostComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:GhostComponent
category: modding-wiki
---

# GhostComponent Documentation

This document provides a comprehensive guide to the `GhostComponent` in Noita modding. Understanding this component is crucial for creating entities that can interact with the game world in unique ways, such as creating temporary visual effects, projectiles, or even complex AI behaviors. This documentation aims to clarify its properties and usage for AI-assisted mod development.

## Overview of GhostComponent

The `GhostComponent` is a fundamental component used in Noita to define entities that are "ghostly" or ephemeral. These entities often exist for a limited duration, have specific visual properties, and can interact with the game world without necessarily being solid or permanent. This makes them ideal for effects like spell trails, temporary platforms, or projectile impacts.

## Component Properties

The `GhostComponent` has several properties that can be configured to control the behavior and appearance of the ghost entity.

### `is_ghost`

*   **Type:** `bool`
*   **Description:** This is the primary flag that designates an entity as a ghost. If `true`, the entity will be treated as a ghost by the game engine.

### `lifetime`

*   **Type:** `float`
*   **Description:** The duration in seconds for which the ghost entity will exist before being automatically removed from the game. A value of `0` or less typically means the ghost will persist indefinitely until manually removed.

### `fade_out_time`

*   **Type:** `float`
*   **Description:** The duration in seconds over which the ghost entity will fade out visually before disappearing completely. This provides a smoother visual transition.

### `sprite_file`

*   **Type:** `string`
*   **Description:** The path to the sprite file (e.g., `.png`) that will be used for the ghost entity's visual representation.

### `sprite_animation_file`

*   **Type:** `string`
*   **Description:** The path to the animation file (e.g., `.xml`) that defines animations for the ghost entity's sprite. This is used if the ghost has animated visuals.

### `sprite_animation_speed`

*   **Type:** `float`
*   **Description:** The speed multiplier for the sprite animation. A value of `1.0` is normal speed.

### `sprite_frame_speed`

*   **Type:** `float`
*   **Description:** The speed at which individual frames of the sprite animation are displayed.

### `sprite_random_start_frame`

*   **Type:** `bool`
*   **Description:** If `true`, the ghost entity's animation will start at a random frame.

### `sprite_flip_x`

*   **Type:** `bool`
*   **Description:** If `true`, the ghost sprite will be flipped horizontally.

### `sprite_flip_y`

*   **Type:** `bool`
*   **Description:** If `true`, the ghost sprite will be flipped vertically.

### `sprite_rotation`

*   **Type:** `float`
*   **Description:** The initial rotation of the ghost sprite in degrees.

### `sprite_scale_x`

*   **Type:** `float`
*   **Description:** The scaling factor for the ghost sprite along the X-axis.

### `sprite_scale_y`

*   **Type:** `float`
*   **Description:** The scaling factor for the ghost sprite along the Y-axis.

### `sprite_offset_x`

*   **Type:** `float`
*   **Description:** An offset applied to the ghost sprite's position along the X-axis.

### `sprite_offset_y`

*   **Type:** `float`
*   **Description:** An offset applied to the ghost sprite's position along the Y-axis.

### `color`

*   **Type:** `Color` (represented as a table with `r`, `g`, `b`, `a` values between 0 and 1)
*   **Description:** The color tint applied to the ghost sprite.

### `material`

*   **Type:** `string`
*   **Description:** The material to apply to the ghost entity. This can affect its visual properties and interactions. Common values include "default", "glass", "ice", etc.

### `physics_material`

*   **Type:** `string`
*   **Description:** The physics material to apply to the ghost entity. This affects how it interacts with other physical objects.

### `damage_by_touch`

*   **Type:** `float`
*   **Description:** The amount of damage the ghost entity inflicts on other entities it touches.

### `damage_by_projectile`

*   **Type:** `float`
*   **Description:** The amount of damage the ghost entity inflicts on projectiles that hit it.

### `damage_by_explosion`

*   **Type:** `float`
*   **Description:** The amount of damage the ghost entity inflicts on entities within its explosion radius.

### `explosion_radius`

*   **Type:** `float`
*   **Description:** The radius of the explosion effect when the ghost entity is destroyed or interacts with certain elements.

### `explosion_damage`

*   **Type:** `float`
*   **Description:** The damage dealt by the explosion effect.

### `explosion_force`

*   **Type:** `float`
*   **Description:** The force applied by the explosion effect.

### `explosion_material`

*   **Type:** `string`
*   **Description:** The material of the explosion effect.

### `explosion_child_entity`

*   **Type:** `string`
*   **Description:** The ID of an entity to spawn at the center of the explosion.

### `explosion_child_entity_radius`

*   **Type:** `float`
*   **Description:** The radius within which the `explosion_child_entity` will be spawned.

### `explosion_child_entity_count`

*   **Type:** `int`
*   **Description:** The number of `explosion_child_entity` instances to spawn.

### `explosion_child_entity_random_offset`

*   **Type:** `float`
*   **Description:** A random offset applied to the spawn position of `explosion_child_entity`.

### `explosion_child_entity_lifetime`

*   **Type:** `float`
*   **Description:** The lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_damage`

*   **Type:** `float`
*   **Description:** The damage dealt by the spawned `explosion_child_entity`.

### `explosion_child_entity_force`

*   **Type:** `float`
*   **Description:** The force applied by the spawned `explosion_child_entity`.

### `explosion_child_entity_material`

*   **Type:** `string`
*   **Description:** The material of the spawned `explosion_child_entity`.

### `explosion_child_entity_color`

*   **Type:** `Color` (represented as a table with `r`, `g`, `b`, `a` values between 0 and 1)
*   **Description:** The color tint of the spawned `explosion_child_entity`.

### `explosion_child_entity_scale_x`

*   **Type:** `float`
*   **Description:** The scaling factor for the spawned `explosion_child_entity` along the X-axis.

### `explosion_child_entity_scale_y`

*   **Type:** `float`
*   **Description:** The scaling factor for the spawned `explosion_child_entity` along the Y-axis.

### `explosion_child_entity_random_rotation`

*   **Type:** `bool`
*   **Description:** If `true`, the spawned `explosion_child_entity` will have a random rotation.

### `explosion_child_entity_random_scale`

*   **Type:** `bool`
*   **Description:** If `true`, the spawned `explosion_child_entity` will have a random scale.

### `explosion_child_entity_random_color`

*   **Type:** `bool`
*   **Description:** If `true`, the spawned `explosion_child_entity` will have a random color.

### `explosion_child_entity_random_material`

*   **Type:** `bool`
*   **Description:** If `true`, the spawned `explosion_child_entity` will have a random material.

### `explosion_child_entity_random_physics_material`

*   **Type:** `bool`
*   **Description:** If `true`, the spawned `explosion_child_entity` will have a random physics material.

### `explosion_child_entity_random_flip_x`

*   **Type:** `bool`
*   **Description:** If `true`, the spawned `explosion_child_entity` will have a random horizontal flip.

### `explosion_child_entity_random_flip_y`

*   **Type:** `bool`
*   **Description:** If `true`, the spawned `explosion_child_entity` will have a random vertical flip.

### `explosion_child_entity_random_offset_x`

*   **Type:** `float`
*   **Description:** A random offset applied to the X position of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y`

*   **Type:** `float`
*   **Description:** A random offset applied to the Y position of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime`

*   **Type:** `float`
*   **Description:** A random variation applied to the lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage`

*   **Type:** `float`
*   **Description:** A random variation applied to the damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force`

*   **Type:** `float`
*   **Description:** A random variation applied to the force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x`

*   **Type:** `float`
*   **Description:** A random variation applied to the X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y`

*   **Type:** `float`
*   **Description:** A random variation applied to the Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r`

*   **Type:** `float`
*   **Description:** A random variation applied to the red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g`

*   **Type:** `float`
*   **Description:** A random variation applied to the green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b`

*   **Type:** `float`
*   **Description:** A random variation applied to the blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a`

*   **Type:** `float`
*   **Description:** A random variation applied to the alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_max`

*   **Type:** `float`
*   **Description:** The maximum random offset for the X position of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_max`

*   **Type:** `float`
*   **Description:** The maximum random offset for the Y position of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_max`

*   **Type:** `float`
*   **Description:** The maximum random variation for the lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_max`

*   **Type:** `float`
*   **Description:** The maximum random variation for the damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_max`

*   **Type:** `float`
*   **Description:** The maximum random variation for the force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_max`

*   **Type:** `float`
*   **Description:** The maximum random variation for the X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max`

*   **Type:** `float`
*   **Description:** The maximum random variation for the Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max`

*   **Type:** `float`
*   **Description:** The maximum random variation for the red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max`

*   **Type:** `float`
*   **Description:** The maximum random variation for the green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max`

*   **Type:** `float`
*   **Description:** The maximum random variation for the blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max`

*   **Type:** `float`
*   **Description:** The maximum random variation for the alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min`

*   **Type:** `float`
*   **Description:** The minimum random offset for the X position of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min`

*   **Type:** `float`
*   **Description:** The minimum random offset for the Y position of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min`

*   **Type:** `float`
*   **Description:** The minimum random variation for the lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min`

*   **Type:** `float`
*   **Description:** The minimum random variation for the damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min`

*   **Type:** `float`
*   **Description:** The minimum random variation for the force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min`

*   **Type:** `float`
*   **Description:** The minimum random variation for the X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min`

*   **Type:** `float`
*   **Description:** The minimum random variation for the Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min`

*   **Type:** `float`
*   **Description:** The minimum random variation for the red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min`

*   **Type:** `float`
*   **Description:** The minimum random variation for the green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min`

*   **Type:** `float`
*   **Description:** The minimum random variation for the blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min`

*   **Type:** `float`
*   **Description:** The minimum random variation for the alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_range`

*   **Type:** `float`
*   **Description:** The range of random offset for the X position of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_range`

*   **Type:** `float`
*   **Description:** The range of random offset for the Y position of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_range`

*   **Type:** `float`
*   **Description:** The range of random variation for the lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_range`

*   **Type:** `float`
*   **Description:** The range of random variation for the damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_range`

*   **Type:** `float`
*   **Description:** The range of random variation for the force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_range`

*   **Type:** `float`
*   **Description:** The range of random variation for the X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_range`

*   **Type:** `float`
*   **Description:** The range of random variation for the Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_range`

*   **Type:** `float`
*   **Description:** The range of random variation for the red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_range`

*   **Type:** `float`
*   **Description:** The range of random variation for the green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_range`

*   **Type:** `float`
*   **Description:** The range of random variation for the blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_range`

*   **Type:** `float`
*   **Description:** The range of random variation for the alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_rotation_range`

*   **Type:** `float`
*   **Description:** The range of random rotation for the spawned `explosion_child_entity`.

### `explosion_child_entity_random_flip_x_range`

*   **Type:** `float`
*   **Description:** The range of random horizontal flip for the spawned `explosion_child_entity`.

### `explosion_child_entity_random_flip_y_range`

*   **Type:** `float`
*   **Description:** The range of random vertical flip for the spawned `explosion_child_entity`.

### `explosion_child_entity_random_material_range`

*   **Type:** `float`
*   **Description:** The range of random material for the spawned `explosion_child_entity`.

### `explosion_child_entity_random_physics_material_range`

*   **Type:** `float`
*   **Description:** The range of random physics material for the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_range`

*   **Type:** `float`
*   **Description:** The minimum range for the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_range`

*   **Type:** `float`
*   **Description:** The minimum range for the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_range`

*   **Type:** `float`
*   **Description:** The minimum range for the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_range`

*   **Type:** `float`
*   **Description:** The minimum range for the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_range`

*   **Type:** `float`
*   **Description:** The minimum range for the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_range`

*   **Type:** `float`
*   **Description:** The minimum range for the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_range`

*   **Type:** `float`
*   **Description:** The maximum range for the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_range`

*   **Type:** `float`
*   **Description:** The maximum range for the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_range`

*   **Type:** `float`
*   **Description:** The maximum range for the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_range`

*   **Type:** `float`
*   **Description:** The maximum range for the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_range`

*   **Type:** `float`
*   **Description:** The maximum range for the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_range`

*   **Type:** `float`
*   **Description:** The maximum range for the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_range_range`

*   **Type:** `float`
*   **Description:** The range of the random range for the X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_range_range`

*   **Type:** `float`
*   **Description:** The range of the random range for the Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_range_range`

*   **Type:** `float`
*   **Description:** The range of the random range for the red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_range_range`

*   **Type:** `float`
*   **Description:** The range of the random range for the green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_range_range`

*   **Type:** `float`
*   **Description:** The range of the random range for the blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_range_range`

*   **Type:** `float`
*   **Description:** The range of the random range for the alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_range`

*   **Type:** `float`
*   **Description:** The minimum range for the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_range`

*   **Type:** `float`
*   **Description:** The minimum range for the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_range`

*   **Type:** `float`
*   **Description:** The minimum range for the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_range`

*   **Type:** `float`
*   **Description:** The minimum range for the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_range`

*   **Type:** `float`
*   **Description:** The minimum range for the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_range`

*   **Type:** `float`
*   **Description:** The minimum range for the minimum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_range_range`

*   **Type:** `float`
*   **Description:** The minimum range for the minimum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_range_range`

*   **Type:** `float`
*   **Description:** The minimum range for the minimum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_range_range`

*   **Type:** `float`
*   **Description:** The minimum range for the minimum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_range_range`

*   **Type:** `float`
*   **Description:** The minimum range for the minimum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_range_range`

*   **Type:** `float`
*   **Description:** The minimum range for the minimum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_max_range`

*   **Type:** `float`
*   **Description:** The maximum range for the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_max_range`

*   **Type:** `float`
*   **Description:** The maximum range for the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_max_range`

*   **Type:** `float`
*   **Description:** The maximum range for the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_max_range`

*   **Type:** `float`
*   **Description:** The maximum range for the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_max_range`

*   **Type:** `float`
*   **Description:** The maximum range for the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_max_range`

*   **Type:** `float`
*   **Description:** The maximum range for the minimum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_range_range`

*   **Type:** `float`
*   **Description:** The maximum range for the minimum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_max_range`

*   **Type:** `float`
*   **Description:** The maximum range for the minimum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_max_range`

*   **Type:** `float`
*   **Description:** The maximum range for the minimum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_max_range`

*   **Type:** `float`
*   **Description:** The maximum range for the minimum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_max_range`

*   **Type:** `float`
*   **Description:** The maximum range for the minimum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_min_range`

*   **Type:** `float`
*   **Description:** The minimum range for the minimum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_min_range`

*   **Type:** `float`
*   **Description:** The minimum range for the minimum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_min_range`

*   **Type:** `float`
*   **Description:** The minimum range for the minimum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_min_range`

*   **Type:** `float`
*   **Description:** The minimum range for the minimum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_min_range`

*   **Type:** `float`
*   **Description:** The minimum range for the minimum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_min_range`

*   **Type:** `float`
*   **Description:** The minimum range for the minimum range of the minimum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_min_range_range`

*   **Type:** `float`
*   **Description:** The minimum range for the minimum range of the minimum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_min_range_range`

*   **Type:** `float`
*   **Description:** The minimum range for the minimum range of the minimum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_min_range_range`

*   **Type:** `float`
*   **Description:** The minimum range for the minimum range of the minimum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_min_range_range`

*   **Type:** `float`
*   **Description:** The minimum range for the minimum range of the minimum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_min_range_range`

*   **Type:** `float`
*   **Description:** The minimum range for the minimum range of the minimum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_max_min_range`

*   **Type:** `float`
*   **Description:** The maximum range for the minimum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_max_min_range`

*   **Type:** `float`
*   **Description:** The maximum range for the minimum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_max_min_range`

*   **Type:** `float`
*   **Description:** The maximum range for the minimum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_max_min_range`

*   **Type:** `float`
*   **Description:** The maximum range for the minimum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_max_min_range`

*   **Type:** `float`
*   **Description:** The maximum range for the minimum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the minimum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the minimum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the minimum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the minimum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the minimum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the minimum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the minimum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the minimum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the minimum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the minimum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the minimum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the minimum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_min_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_min_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_offset_x_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset X of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_offset_y_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random offset Y of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_lifetime_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random lifetime of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_damage_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random damage of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_force_min_max_max_max_max_range`

*   **Type:** `float`
*   **Description:** The minimum range for the maximum range of the random force of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_x_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random Y scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_color_r_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random red component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_g_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random green component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_b_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random blue component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_color_a_min_min_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the minimum range for the maximum range of the random alpha component of the spawned `explosion_child_entity`'s color.

### `explosion_child_entity_random_scale_x_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of the maximum range for the maximum range of the random X scale of the spawned `explosion_child_entity`.

### `explosion_child_entity_random_scale_y_max_max_max_max_max_range_range`

*   **Type:** `float`
*   **Description:** The range of