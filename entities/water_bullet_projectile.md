---
title: Water Bullet Projectile
category: entities
---

# Water Bullet Projectile

This document details the configuration of the `water_bullet.xml` entity, which defines the behavior and properties of the water projectile in Noita.

## Core Components

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This component inherits fundamental projectile properties.

*   **`gravity_y`**: `100` - Controls the downward acceleration due to gravity.
*   **`air_friction`**: `-0.1` - Affects how air resistance slows the projectile.
*   **`mass`**: `0.07` - The projectile's mass, influencing its interaction with physics.

### Homing Component (`HomingComponent`)

Enables the projectile to track its target.

*   **`homing_targeting_coeff`**: `130.0` - The strength of the homing mechanism. Higher values mean more aggressive tracking.
*   **`homing_velocity_multiplier`**: `0.86` - Adjusts the projectile's speed when actively homing.

### Projectile Component (`ProjectileComponent`)

Defines the specific characteristics of the water bullet.

*   **`lob_min` / `lob_max`**: `0.5` / `0.7` - Controls the minimum and maximum arc of the projectile's trajectory.
*   **`speed_min` / `speed_max`**: `600` / `650` - The range of initial velocities for the projectile.
*   **`lifetime`**: `40` - The duration in frames before the projectile expires.
*   **`lifetime_randomness`**: `7` - Adds variability to the projectile's lifetime.
*   **`damage`**: `0` - The projectile deals no direct damage.
*   **`on_death_explode`**: `1` - The projectile explodes upon death.
*   **`on_lifetime_out_explode`**: `1` - The projectile explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter`**: `1` - Prevents the explosion from harming the entity that fired it.
*   **`on_collision_die`**: `1` - The projectile is destroyed upon collision.
*   **`knockback_force`**: `1.8` - The force applied to entities upon collision.
*   **`muzzle_flash_file`**: `data/entities/particles/muzzle_flashes/muzzle_flash.xml` - Specifies the visual effect for the muzzle flash.
*   **`shoot_light_flash_r/g/b/radius`**: `255/125/80/72` - Defines the color and radius of the light flash when fired.

#### `config_explosion` (Nested within `ProjectileComponent`)

Details the properties of the explosion that occurs when the projectile dies.

*   **`load_this_entity`**: `data/entities/misc/essences/water_explosion.xml` - The entity to load and spawn upon explosion.
*   **`damage`**: `0` - The explosion itself deals no damage.
*   **`camera_shake`**: `0` - No camera shake is triggered by the explosion.
*   **`hole_enabled`**: `1` - The explosion can create holes in terrain.
*   **`ray_energy`**: `2000` - The energy of rays emitted by the explosion.
*   **`max_durability_to_destroy`**: `8` - The maximum durability of terrain that can be destroyed by the explosion.
*   **`physics_explosion_power.min/max`**: `0.02` / `0.1` - The minimum and maximum physics force applied by the explosion.

### Particle Emitter (`ParticleEmitterComponent`)

Responsible for generating visual effects.

*   **`emitted_material_name`**: `spark` - The type of particle to emit.
*   **`is_trail`**: `1` - The particles form a trail.
*   **`count_min/max`**: `1` / `1` - Emits a single particle per emission.
*   **`lifetime_min/max`**: `1.0` / `1.5` - The duration of each emitted particle.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`create_real_particles`**: `0` - These are cosmetic particles, not physical entities.

### Audio Component (`AudioComponent`)

Manages the sound effects associated with the projectile.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound events.
*   **`event_root`**: `player_projectiles/bullet` - The root event for player projectile sounds.