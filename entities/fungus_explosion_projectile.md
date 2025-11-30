---
title: Fungus Explosion Projectile
category: entities
---

# Fungus Explosion Projectile

This document details the configuration of the `fungus_explosion.xml` entity, which defines a projectile that explodes upon death or collision, leaving behind fungal material and causing a localized explosion effect.

## Core Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile properties.

*   **`gravity_y`**: `100` - Controls the vertical acceleration due to gravity.

### Projectile Component (`<ProjectileComponent>`)

This is the primary component defining the projectile's behavior and explosion characteristics.

*   **`_enabled`**: `1` - Enables the component.
*   **`lob_min` / `lob_max`**: `0.8` / `1.0` - Defines the minimum and maximum lobbing behavior (arc of trajectory).
*   **`speed_min` / `speed_max`**: `160` / `170` - Sets the projectile's initial speed range.
*   **`on_death_explode`**: `1` - Triggers an explosion when the projectile dies (e.g., due to lifetime or low velocity).
*   **`on_lifetime_out_explode`**: `1` - Triggers an explosion when the projectile's lifetime expires.
*   **`damage`**: `0.5` - The base damage dealt by the projectile itself before explosion.
*   **`lifetime`**: `1` - The duration in seconds before the projectile expires.
*   **`on_collision_die`**: `1` - The projectile will be destroyed upon colliding with an entity.
*   **`die_on_low_velocity`**: `1` - The projectile will die if its velocity drops below a certain threshold.

#### Explosion Configuration (`<config_explosion>`)

Defines the parameters of the explosion effect.

*   **`camera_shake`**: `10` - The intensity of camera shake during the explosion.
*   **`explosion_radius`**: `50` - The radius of the explosion's effect.
*   **`explosion_sprite`**: `data/particles/explosion_025_fuel.xml` - The visual sprite used for the explosion effect.
*   **`load_this_entity`**: `data/entities/particles/particle_explosion/main_pink.xml` - The entity to load and spawn as part of the explosion.
*   **`create_cell_probability`**: `1` - Probability (100%) of creating a new cell upon explosion.
*   **`create_cell_material`**: `fungi` - The material of the cell to be created.
*   **`hole_enabled`**: `1` - Enables the creation of holes in surfaces by the explosion.
*   **`hole_image`**: `data/temp/explosion_hole.png` - The image used for the explosion hole.
*   **`particle_effect`**: `1` - Enables particle effects associated with the explosion.
*   **`physics_explosion_power.min` / `physics_explosion_power.max`**: `0.6` / `1.0` - The minimum and maximum force applied to physics objects by the explosion.
*   **`physics_throw_enabled`**: `1` - Enables physics objects to be thrown by the explosion.
*   **`shake_vegetation`**: `1` - Causes vegetation to shake during the explosion.
*   **`sparks_count_min` / `sparks_count_max`**: `15` / `30` - The range for the number of sparks generated.
*   **`spark_material`**: `plasma_fading_pink` - The material of the sparks.
*   **`stains_enabled`**: `1` - Enables the creation of stains on surfaces.
*   **`stains_image`**: `data/temp/explosion_stain.png` - The image used for explosion stains.
*   **`ray_energy`**: `60000` - The energy value associated with the explosion's ray interactions.
*   **`audio_event_name`**: `explosions/slime` - The sound event triggered by the explosion.

### Sprite Component (`<SpriteComponent>`)

Defines the visual representation of the projectile.

*   **`_enabled`**: `1` - Enables the component.
*   **`image_file`**: `data/projectiles_gfx/fireball_alt.xml` - The file containing the projectile's sprite animation data.
*   **`offset_x` / `offset_y`**: `16` / `12` - The offset of the sprite from the projectile's origin.

### Particle Emitter Component (`<ParticleEmitterComponent>`)

Responsible for emitting particles during the projectile's flight.

*   **`emitted_material_name`**: `fire` - The material of the particles to be emitted.
*   **`count_min` / `count_max`**: `7` / `15` - The range for the number of particles emitted per emission.
*   **`lifetime_min` / `lifetime_max`**: `0.1` / `0.3` - The duration in seconds for emitted particles.
*   **`create_real_particles`**: `1` - Indicates that actual game particles should be created.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `1` / `2` - The interval in frames between particle emissions.
*   **`is_emitting`**: `1` - Enables the particle emitter.

### Variable Storage Component (`<VariableStorageComponent>`)

Stores custom variables associated with the entity.

*   **`name`**: `projectile_file` - The name of the variable.
*   **`value_string`**: `data/entities/projectiles/fungus_explosion.xml` - The string value, referencing the entity's own file path.