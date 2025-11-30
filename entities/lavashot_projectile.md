---
title: Lavashot Projectile
category: entities
---

# Lavashot Projectile

This document details the configuration of the `lavashot.xml` entity, which defines the behavior and appearance of the lava projectile in Noita.

## Core Components

### Base Projectile (`BaseComponent`)

This component inherits fundamental projectile properties.

*   **`gravity_y`**: `10` - Controls the downward acceleration due to gravity.
*   **`mass`**: `0.07` - The mass of the projectile, influencing its interaction with physics.

### Projectile Behavior (`ProjectileComponent`)

This is the primary component defining the projectile's actions and effects.

*   **`speed_min`**: `130` - The minimum initial velocity of the projectile.
*   **`speed_max`**: `160` - The maximum initial velocity of the projectile.
*   **`on_death_explode`**: `1` - The projectile will explode upon death.
*   **`on_lifetime_out_explode`**: `1` - The projectile will explode when its lifetime expires.
*   **`on_collision_die`**: `1` - The projectile will die upon colliding with something.
*   **`die_on_low_velocity`**: `1` - The projectile will die if its velocity drops too low.
*   **`damage`**: `1.5` - The base damage dealt by the projectile.
*   **`lifetime`**: `330` - The duration in frames before the projectile expires.
*   **`knockback_force`**: `2.0` - The force applied to knock back entities upon collision.

#### Explosion Configuration (`config_explosion`)

Defines the parameters of the explosion that occurs when the projectile dies.

*   **`camera_shake`**: `4.5` - The intensity of camera shake during the explosion.
*   **`explosion_radius`**: `9` - The radius of the explosion's effect.
*   **`explosion_sprite`**: `data/particles/explosion_032.xml` - The visual effect used for the explosion.
*   **`create_cell_material`**: `lava` - The material created by the explosion (e.g., lava pools).
*   **`create_cell_probability`**: `40` - The percentage chance of creating the specified cell material.
*   **`hole_enabled`**: `1` - Enables the creation of holes in terrain by the explosion.
*   **`hole_image`**: `data/temp/explosion_hole.png` - The image used for the terrain hole.
*   **`audio_event_name`**: `explosions/tnt` - The sound event triggered by the explosion.
*   **`damage_mortals`**: `1` - The explosion deals damage to living entities.
*   **`physics_explosion_power.max`**: `0.4` - The maximum force applied to physics objects during the explosion.
*   **`stains_enabled`**: `1` - Enables the creation of impact stains.
*   **`stains_radius`**: `9` - The radius of the impact stains.

### Visual Representation (`SpriteComponent`)

Defines the visual appearance of the projectile.

*   **`image_file`**: `data/projectiles_gfx/lavashot.xml` - The sprite sheet or animation definition for the projectile.
*   **`emissive`**: `1` - The sprite is emissive, meaning it emits light.
*   **`additive`**: `1` - The sprite uses additive blending, making it appear brighter when overlapping.

### Particle Emitters (`ParticleEmitterComponent`)

These components generate visual particle effects associated with the projectile.

#### Lava Particles

*   **`emitted_material_name`**: `lava` - The material of the particles emitted.
*   **`offset.y`**: `5` - The vertical offset for particle emission.
*   **`x_vel_min`/`max`, `y_vel_min`/`max`**: Defines the velocity range of emitted particles.
*   **`lifetime_min`/`max`**: `0.1` to `0.3` - The duration of each particle.
*   **`create_real_particles`**: `1` - Emits actual game particles.
*   **`emission_interval_min_frames`/`max_frames`**: `5` to `8` - Controls the rate of emission.

#### Fire Particles

*   **`emitted_material_name`**: `fire` - The material of the particles emitted.
*   **`x_vel_min`/`max`, `y_vel_min`/`max`**: Defines the velocity range of emitted particles.
*   **`lifetime_min`/`max`**: `0.1` to `0.3` - The duration of each particle.
*   **`create_real_particles`**: `1` - Emits actual game particles.
*   **`emission_interval_min_frames`/`max_frames`**: `1` to `2` - Controls the rate of emission.

### Hitbox (`HitboxComponent`)

Defines the collision area of the projectile.

*   **`aabb_min_x`/`y`**: `-5` - The minimum X and Y coordinates of the bounding box.
*   **`aabb_max_x`/`y`**: `5` - The maximum X and Y coordinates of the bounding box.

### Damage Model (`DamageModelComponent`)

Configures how the projectile interacts with damage and other entities.

*   **`hp`**: `0.6` - The health of the projectile itself.
*   **`blood_material`**: `lava` - The material that appears when the projectile is damaged (though it has 0.6 HP, this might be for specific interactions).
*   **`create_ragdoll`**: `0` - The projectile does not create a ragdoll upon destruction.

### Audio (`AudioComponent`)

Defines the sound effects associated with the projectile.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound event.
*   **`event_root`**: `projectiles/bullet_fire_heavy` - The specific sound event to play.

### Variable Storage (`VariableStorageComponent`)

Stores custom variables for the entity.

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/projectiles/lavashot.xml` - Stores the path to this entity's XML file.