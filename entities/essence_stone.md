---
title: Essence Stone
category: entities
---

# Essence Stone

The Essence Stone is a collectible entity in Noita, primarily functioning as a visual indicator and a trigger for specific game events. It's a small, orb-like object with a distinct visual appearance and a defined hitbox.

## Key Components and Attributes

### SpriteComponent
This component defines the visual representation of the Essence Stone.

*   `image_file`: Specifies the graphical asset used for the orb.
*   `offset_x`, `offset_y`: Controls the positioning of the sprite relative to the entity's origin.
*   `special_scale_x`, `special_scale_y`: Allows for non-uniform scaling of the sprite.
*   `alpha`: Controls the transparency of the sprite.
*   `rect_animation`: Defines the animation state, here set to "stand".

### HitboxComponent
This component defines the physical boundaries of the Essence Stone for collision detection.

*   `aabb_min_x`, `aabb_max_x`: Defines the minimum and maximum X-coordinates of the Axis-Aligned Bounding Box (AABB).
*   `aabb_min_y`, `aabb_max_y`: Defines the minimum and maximum Y-coordinates of the AABB.

### DamageModelComponent
This component handles how the Essence Stone reacts to damage.

*   `hp`: The health points of the Essence Stone.
*   `fire_damage_amount`: The amount of fire damage it takes.
*   `critical_damage_resistance`: Resistance to critical hits.
*   `materials_damage`: Whether it takes damage from contact with certain materials.
*   `damage_multipliers`: Specific multipliers for different damage types (e.g., `melee`).

### ExplodeOnDamageComponent
This component dictates the behavior of the Essence Stone when it takes damage, specifically when it's set to explode.

*   `explode_on_death_percent`: The percentage of health at which the entity explodes upon death.
*   `explode_on_damage_percent`: The percentage of health at which the entity explodes when taking damage (set to 0.0, meaning it only explodes on death).
*   `config_explosion`: A nested configuration for the explosion effect.
    *   `camera_shake`: The intensity of camera shake during the explosion.
    *   `explosion_radius`: The radius of the explosion effect.
    *   `load_this_entity`: The entity to spawn upon explosion (e.g., particle effects).
    *   `ray_energy`: The energy of any rays emitted by the explosion.
    *   `physics_explosion_power`: The minimum and maximum power of the physics-based explosion.
    *   `sparks_count_min`, `sparks_count_max`: The range for the number of sparks generated.
    *   `stains_radius`: The radius of stains left by the explosion.

### UIInfoComponent
This component provides information for the user interface.

*   `name`: The internal name of the item, often used for localization.

### LuaComponent
This component allows for custom scripting behavior.

*   `script_death`: The Lua script to execute when the entity dies. In this case, it's `data/scripts/essences/away.lua`, suggesting a script that handles the entity's removal or a related effect upon death.

### ParticleEmitterComponent
This component is responsible for emitting particles, contributing to visual effects.

*   `emitted_material_name`: The material of the particles to be emitted (e.g., `spark_blue`).
*   `lifetime_min`, `lifetime_max`: The minimum and maximum duration of emitted particles.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: The velocity range for emitted particles.
*   `count_min`, `count_max`: The number of particles emitted per burst.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: The frame interval between particle emissions.
*   `area_circle_radius.max`: The maximum radius of the emission area.
*   `is_emitting`: A flag to enable or disable particle emission.