---
title: Gas Blob Projectile
category: entities
---

# Gas Blob Projectile

This document details the configuration of the `gasblob.xml` entity, which defines a projectile that releases poison gas upon impact or expiration.

## Core Components

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This component defines the fundamental physics properties of the projectile.

*   **`gravity_y`**: `10` - The projectile is affected by gravity.
*   **`air_friction`**: `0` - No air resistance is applied.
*   **`mass`**: `0.055` - The mass of the projectile.

### Projectile (`ProjectileComponent`)

This component governs the behavior and effects of the projectile.

*   **`speed_min`**: `90` - Minimum initial velocity.
*   **`speed_max`**: `115` - Maximum initial velocity.
*   **`on_death_explode`**: `1` - The projectile explodes when it dies.
*   **`on_lifetime_out_explode`**: `1` - The projectile explodes when its lifetime expires.
*   **`on_collision_die`**: `1` - The projectile dies upon collision.
*   **`die_on_low_velocity`**: `1` - The projectile dies if its velocity drops too low.
*   **`damage`**: `0.25` - The base damage dealt by the projectile itself.
*   **`lifetime`**: `130` - The duration in frames before the projectile expires.
*   **`knockback_force`**: `1.5` - The force applied to knock back entities upon collision.

#### Explosion Configuration (`config_explosion`)

Defines the properties of the explosion that occurs upon the projectile's death.

*   **`damage`**: `0.3` - Damage dealt by the explosion.
*   **`camera_shake`**: `3.5` - Intensity of camera shake during the explosion.
*   **`explosion_radius`**: `9` - The radius of the explosion's effect.
*   **`explosion_sprite`**: `data/particles/smoke_cloud_pink_1.xml` - The visual effect used for the explosion.
*   **`create_cell_probability`**: `90` - Percentage chance to create a new cell upon explosion.
*   **`create_cell_material`**: `poison` - The material of the cell created.
*   **`hole_enabled`**: `1` - Enables the creation of holes in terrain.
*   **`hole_image`**: `data/temp/explosion_hole.png` - The image used for the created hole.
*   **`physics_explosion_power.min`**: `0.2` - Minimum physics force applied by the explosion.
*   **`physics_explosion_power.max`**: `0.3` - Maximum physics force applied by the explosion.
*   **`physics_throw_enabled`**: `1` - Entities affected by the explosion can be thrown.
*   **`stains_enabled`**: `1` - Enables the creation of stains from the explosion.
*   **`stains_radius`**: `9` - The radius of the stains.

### Particle Emitter (`ParticleEmitterComponent`)

This component is responsible for emitting `poison_gas` particles.

*   **`emitted_material_name`**: `poison_gas` - The material of the particles being emitted.
*   **`count_min`**: `1` - Minimum number of particles emitted per emission.
*   **`count_max`**: `3` - Maximum number of particles emitted per emission.
*   **`gravity.y`**: `0` - Emitted particles are not affected by gravity.
*   **`x_vel_min`**: `-30` - Minimum horizontal velocity of emitted particles.
*   **`x_vel_max`**: `30` - Maximum horizontal velocity of emitted particles.
*   **`y_vel_min`**: `-30` - Minimum vertical velocity of emitted particles.
*   **`y_vel_max`**: `30` - Maximum vertical velocity of emitted particles.
*   **`is_trail`**: `1` - Particles are emitted as a trail.
*   **`trail_gap`**: `2.5` - The gap between particles in the trail.
*   **`lifetime_min`**: `0.1` - Minimum lifetime of emitted particles.
*   **`lifetime_max`**: `1.3` - Maximum lifetime of emitted particles.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime decreases.
*   **`emit_cosmetic_particles`**: `1` - Emits cosmetic particles for visual effect.
*   **`emission_interval_min_frames`**: `1` - Minimum frames between particle emissions.
*   **`emission_interval_max_frames`**: `1` - Maximum frames between particle emissions.
*   **`is_emitting`**: `1` - The particle emitter is active.

### Light Component (`LightComponent`)

Adds a light source to the projectile.

*   **`radius`**: `30` - The radius of the light.
*   **`r`**: `99` - Red component of the light color.
*   **`g`**: `205` - Green component of the light color.
*   **`b`**: `189` - Blue component of the light color.

### Audio Component (`AudioComponent`)

Defines the sound effects associated with the projectile.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound events.
*   **`event_root`**: `projectiles/slime_gas` - The root event name for projectile sounds.

### Variable Storage (`VariableStorageComponent`)

Stores variables associated with the entity.

*   **`name`**: `projectile_file` - The name of the variable.
*   **`value_string`**: `data/entities/projectiles/gasblob.xml` - The string value, indicating the entity's own file path.