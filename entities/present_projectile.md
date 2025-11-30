---
title: Present Projectile
category: entities
---

# Present Projectile

This document details the configuration of the "Present" projectile entity in Noita, focusing on its behavior and visual components for AI-assisted modding.

## Entity Definition

The core of the projectile is defined by an `<Entity>` tag, inheriting base projectile properties.

```xml
<Entity 
  name="$projectile_default" 
   >
	<Base file="data/entities/base_projectile.xml" >
	</Base>
    <!-- ... other components ... -->
</Entity>
```

## ProjectileComponent

This component governs the projectile's physical and behavioral attributes.

### Key Attributes:

*   **`lob_min`, `lob_max`**: Controls the arc of the projectile. Values are in radians.
    *   `lob_min="0.5"`
    *   `lob_max="1.0"`
*   **`speed_min`, `speed_max`**: Defines the projectile's initial velocity range.
    *   `speed_min="150"`
    *   `speed_max="200"`
*   **`direction_random_rad`**: Introduces slight randomness to the projectile's trajectory.
    *   `direction_random_rad="0.02"`
*   **`on_death_explode`**: Determines if the projectile explodes upon death.
    *   `on_death_explode="1"` (Explodes)
*   **`on_collision_die`**: If true, the projectile is destroyed upon collision.
    *   `on_collision_die="1"` (Dies on collision)
*   **`damage`**: The base damage dealt by the projectile.
    *   `damage="0.0"` (This projectile itself deals no damage)
*   **`lifetime`**: How long the projectile exists before expiring. `-1` means it lasts indefinitely until other conditions are met.
    *   `lifetime="-1"`

### `config_explosion` Sub-element:

This nested element defines the properties of the explosion that occurs when `on_death_explode` is true.

*   **`damage`**: Damage dealt by the explosion.
    *   `damage="2"`
*   **`camera_shake`**: Intensity of camera shake upon explosion.
    *   `camera_shake="25"`
*   **`explosion_radius`**: The radius of the explosion's effect.
    *   `explosion_radius="25"`
*   **`explosion_sprite`**: The visual sprite used for the explosion effect.
    *   `explosion_sprite="data/particles/smoke_01.xml"`
*   **`create_cell_probability`**: Chance to create a material cell at the explosion site.
    *   `create_cell_probability="40"`
*   **`create_cell_material`**: The material of the cell to be created.
    *   `create_cell_material="snow_sticky"`
*   **`ray_energy`**: Energy value for raycasting effects from the explosion.
    *   `ray_energy="150000"`
*   **`physics_explosion_power.min`, `physics_explosion_power.max`**: Controls the force of the physics-based explosion.
    *   `physics_explosion_power.min="1.4"`
    *   `physics_explosion_power.max="2.6"`
*   **`stains_enabled`, `stains_radius`**: Controls whether stains are left and their size.
    *   `stains_enabled="1"`
    *   `stains_radius="15"`

## SpriteComponent

This component defines the visual appearance of the projectile.

*   **`image_file`**: Path to the sprite's XML definition.
    *   `image_file="data/items_gfx/chest_present.xml"`
*   **`offset_x`, `offset_y`**: Adjusts the sprite's position relative to the projectile's origin.
    *   `offset_x="8"`
    *   `offset_y="11"`

## ParticleEmitterComponent

This component is responsible for emitting particles, likely for visual flair upon creation or collision.

*   **`emitted_material_name`**: The material of the particles to be emitted.
    *   `emitted_material_name="snow_sticky"`
*   **`count_min`, `count_max`**: The range for the number of particles emitted per emission.
    *   `count_min="1"`
    *   `count_max="3"`
*   **`x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`**: Defines the velocity range of emitted particles.
    *   `x_vel_min="-10"`
    *   `x_vel_max="10"`
    *   `y_vel_min="-10"`
    *   `y_vel_max="10"`
*   **`lifetime_min`, `lifetime_max`**: Duration for which emitted particles exist.
    *   `lifetime_min="0.1"`
    *   `lifetime_max="0.3"`
*   **`is_emitting`**: Whether the emitter is active.
    *   `is_emitting="1"`

## VariableStorageComponent

This component stores custom variables associated with the entity.

*   **`name`**: The name of the variable.
    *   `name="projectile_file"`
*   **`value_string`**: The string value assigned to the variable. This is often used to reference the entity's own file path.
    *   `value_string="data/entities/projectiles/present.xml"`