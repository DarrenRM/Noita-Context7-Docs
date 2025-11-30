---
title: Fungus Big Explosion Projectile
category: entities
---

---

# Fungus Big Explosion Projectile

This document details the configuration of the `fungus_big_explosion.xml` entity, which defines a projectile that explodes with significant force and particle effects.

## Core Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This element inherits fundamental projectile properties.

*   **`gravity_y`**: `100` - Applies a moderate downward gravitational pull to the projectile.

### Projectile Component (`<ProjectileComponent>`)

This is the primary component defining the projectile's behavior and effects.

*   **`_enabled`**: `1` - Ensures the projectile component is active.
*   **`lob_min` / `lob_max`**: `0.8` / `1.0` - Controls the lobbing behavior, indicating a relatively straight trajectory with minimal arc.
*   **`speed_min` / `speed_max`**: `160` / `170` - Sets the initial velocity range of the projectile.
*   **`on_death_explode`**: `1` - Triggers an explosion when the projectile dies.
*   **`on_lifetime_out_explode`**: `1` - Triggers an explosion when the projectile's lifetime expires.
*   **`damage`**: `0.5` - The base damage dealt by the projectile upon explosion.
*   **`lifetime`**: `1` - The duration in seconds before the projectile expires and explodes.
*   **`die_on_low_velocity`**: `1` - The projectile will die if its velocity drops too low.
*   **`on_collision_die`**: `1` - The projectile will die upon colliding with something.
*   **`explosion_dont_damage_shooter`**: `0` - The explosion *can* damage the entity that fired it.

#### Explosion Configuration (`<config_explosion>`)

Defines the parameters of the explosion effect.

*   **`camera_shake`**: `40` - The intensity of camera shake upon explosion.
*   **`explosion_radius`**: `60` - The radius of the explosion's effect.
*   **`explosion_sprite`**: `data/particles/explosion_025_fuel.xml` - The sprite used for the explosion's visual effect.
*   **`load_this_entity`**: `data/entities/particles/particle_explosion/main_pink.xml` - The entity to load for the main explosion particle effect.
*   **`create_cell_probability`**: `2` - The probability of creating fungal cells upon explosion.
*   **`create_cell_material`**: `fungi` - The material of the cells created.
*   **`hole_enabled`**: `1` - Enables the creation of holes in terrain by the explosion.
*   **`hole_image`**: `data/temp/explosion_hole.png` - The image used for the explosion hole.
*   **`particle_effect`**: `1` - Enables general particle effects for the explosion.
*   **`physics_explosion_power.min` / `physics_explosion_power.max`**: `0.8` / `1.8` - The minimum and maximum force applied to physics objects by the explosion.
*   **`physics_throw_enabled`**: `1` - Enables physics objects to be thrown by the explosion.
*   **`sparks_count_min` / `sparks_count_max`**: `35` / `50` - The range for the number of sparks generated.
*   **`spark_material`**: `plasma_fading_pink` - The material of the sparks.
*   **`stains_enabled`**: `1` - Enables the creation of stains on surfaces.
*   **`stains_image`**: `data/temp/explosion_stain.png` - The image used for stains.
*   **`ray_energy`**: `6000000` - The energy value associated with the explosion's ray effects.
*   **`max_durability_to_destroy`**: `12` - The maximum durability of objects that can be destroyed by the explosion.
*   **`audio_event_name`**: `explosions/slime` - The sound event triggered by the explosion.

### Sprite Component (`<SpriteComponent>`)

Defines the visual representation of the projectile.

*   **`image_file`**: `data/projectiles_gfx/fireball_alt.xml` - The sprite asset used for the projectile.
*   **`offset_x` / `offset_y`**: `16` / `12` - Adjusts the sprite's position relative to the projectile's origin.

### Particle Emitter Component (`<ParticleEmitterComponent>`)

Responsible for emitting particles during the projectile's flight.

*   **`emitted_material_name`**: `fire` - The material of the particles being emitted.
*   **`count_min` / `count_max`**: `7` / `15` - The range for the number of particles emitted per burst.
*   **`lifetime_min` / `lifetime_max`**: `0.1` / `0.3` - The duration of each emitted particle.
*   **`create_real_particles`**: `1` - Indicates that actual game particles should be created.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `1` / `2` - The frame interval between particle emissions.
*   **`is_emitting`**: `1` - Ensures the particle emitter is active.

### Variable Storage Component (`<VariableStorageComponent>`)

Stores custom variables associated with the entity.

*   **`name`**: `projectile_file` - The name of the variable.
*   **`value_string`**: `data/entities/projectiles/fungus_big_explosion.xml` - The string value, referencing the entity's own file path.