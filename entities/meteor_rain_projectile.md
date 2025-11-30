---
title: Meteor Rain Projectile
category: entities
---

# Meteor Rain Projectile

This document describes the `meteor_rain_meteor.xml` entity, which defines the behavior and appearance of the meteor projectile used in Noita.

## Core Components

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This component inherits fundamental projectile properties.

*   **`gravity_y`**: `50` - The projectile is significantly affected by gravity.
*   **`air_friction`**: `0` - No air resistance is applied.
*   **`mass`**: `0.3` - A relatively low mass.

### Lua Component (`LuaComponent`)

This component enables custom scripting for projectile behavior.

*   **`script_source_file`**: `data/scripts/projectiles/meteor_collide.lua` - The script handling collision logic.
*   **`execute_every_n_frame`**: `20` - The script runs every 20 frames.
*   **`remove_after_executed`**: `1` - The projectile is removed after the script executes.

### Projectile Component (`ProjectileComponent`)

This is the primary component defining the projectile's characteristics.

*   **`lob_min` / `lob_max`**: `0.8` / `1.0` - Controls the arc of the projectile.
*   **`speed_min` / `speed_max`**: `300` / `400` - The initial velocity range.
*   **`die_on_low_velocity`**: `1` - The projectile is destroyed if its velocity drops too low.
*   **`on_death_explode`**: `1` - The projectile explodes upon death.
*   **`on_lifetime_out_explode`**: `1` - The projectile explodes when its lifetime expires.
*   **`friendly_fire`**: `1` - The projectile can damage the shooter.
*   **`damage`**: `0` - Base damage is zero, likely relying on explosion for damage.
*   **`lifetime`**: `120` - The projectile exists for 120 frames.
*   **`knockback_force`**: `3.0` - The force applied to knock back entities.
*   **`penetrate_world`**: `1` - The projectile can pass through terrain.

#### Damage by Type (`damage_by_type`)

*   **`fire`**: `2.25` - Deals 2.25 damage of type fire.

#### Explosion Configuration (`config_explosion`)

*   **`camera_shake`**: `20.5` - The intensity of camera shake upon explosion.
*   **`explosion_radius`**: `45` - The radius of the explosion.
*   **`explosion_sprite`**: `data/particles/explosion_040_poof.xml` - The visual effect of the explosion.
*   **`create_cell_probability`**: `100` - Always creates material cells.
*   **`create_cell_material`**: `fire` - Creates fire material cells.
*   **`load_this_entity`**: `data/entities/particles/particle_explosion/main.xml,data/entities/misc/loose_ground.xml,data/entities/misc/explosion_was_here.xml` - Entities spawned by the explosion.
*   **`ray_energy`**: `7500000` - The energy of the explosion's damaging rays.
*   **`hole_enabled`**: `1` - Creates holes in terrain.
*   **`damage_mortals`**: `1` - Damages living entities.
*   **`physics_explosion_power.min` / `max`**: `2` / `4` - The minimum and maximum physics force of the explosion.
*   **`sparks_count_min` / `max`**: `50` / `100` - The number of sparks generated.

### Sprite Component (`SpriteComponent`)

Defines the visual representation of the projectile.

*   **`image_file`**: `data/projectiles_gfx/meteor.xml` - The sprite asset for the meteor.
*   **`emissive`**: `1` - The sprite emits light.
*   **`additive`**: `1` - The sprite uses additive blending.
*   **`z_index`**: `-0.5` - Renders the sprite slightly behind other elements.

## Particle Emitters

The meteor projectile utilizes several `ParticleEmitterComponent`s to create visual effects.

### Smoke Emitter

*   **`emitted_material_name`**: `smoke`
*   **`count_min` / `max`**: `5` / `5`
*   **`lifetime_min` / `max`**: `0.1` / `0.3`

### Fire Emitter (Initial Burst)

*   **`emitted_material_name`**: `fire`
*   **`count_min` / `max`**: `1` / `1`
*   **`lifetime_min` / `max`**: `0.1` / `0.3`

### Fire Emitter (Delayed)

*   **`emitted_material_name`**: `fire`
*   **`custom_style`**: `FIRE`
*   **`count_min` / `max`**: `6` / `6`
*   **`lifetime_min` / `max`**: `1.1` / `2.8`
*   **`delay_frames`**: `2`

### Spark Emitter

*   **`emitted_material_name`**: `spark`
*   **`count_min` / `max`**: `40` / `100`
*   **`lifetime_min` / `max`**: `0.2` / `0.4`
*   **`airflow_force`**: `2.5`
*   **`airflow_time`**: `1.401`
*   **`emit_cosmetic_particles`**: `1`
*   **`create_real_particles`**: `0`

### Fire Emitter (Explosion Sparks)

*   **`emitted_material_name`**: `fire`
*   **`count_min` / `max`**: `80` / `120`
*   **`lifetime_min` / `max`**: `0.1` / `0.2`
*   **`airflow_force`**: `8.5`
*   **`airflow_time`**: `1.401`
*   **`emit_cosmetic_particles`**: `1`
*   **`create_real_particles`**: `0`

### Sprite Particle Emitter (Fire)

*   **`sprite_file`**: `data/particles/fire_large.xml`
*   **`count_min` / `max`**: `3` / `5`
*   **`randomize_position.min_x` / `max_x`**: `-7` / `7`
*   **`randomize_position.min_y` / `max_y`**: `-7` / `7`
*   **`randomize_velocity.min_x` / `max_x`**: `-10` / `10`
*   **`randomize_velocity.min_y` / `max_y`**: `-10` / `10`

## Other Components

### Light Component (`LightComponent`)

*   **`radius`**: `150` - The radius of the light emitted by the projectile.

### Audio Component (`AudioComponent`)

*   **`file`**: `data/audio/Desktop/projectiles.bank`
*   **`event_root`**: `player_projectiles/meteor` - Plays the sound for the meteor projectile.

### Audio Loop Component (`AudioLoopComponent`)

*   **`file`**: `data/audio/Desktop/projectiles.bank`
*   **`event_name`**: `player_projectiles/meteor/loop` - Plays a looping sound for the meteor.

### Variable Storage Component (`VariableStorageComponent`)

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/projectiles/deck/meteor.xml` - Stores the reference to the base meteor projectile file.