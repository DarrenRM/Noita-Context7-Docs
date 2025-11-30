---
title: Boss Spirit Orb Projectile
category: entities
---

# Boss Spirit Orb Projectile

This document describes the `orb.xml` entity, which defines a projectile used by the Boss Spirit. It's a special projectile with unique visual and behavioral properties.

## Key Attributes

This projectile is primarily defined by its `ProjectileComponent` and `SpriteComponent`, along with several other components that contribute to its visual effects, sound, and behavior.

### Entity Name and Tags

*   **name**: `$projectile_default` (This is a generic projectile name, the specific behavior is defined by its components)
*   **tags**: `boss_alchemist` (Indicates this projectile is associated with the boss alchemist)

### Base Projectile Configuration

*   **file**: `data/entities/base_projectile.xml` (Inherits fundamental projectile properties)
    *   **VelocityComponent**:
        *   `gravity_y`: `0` (No vertical gravity applied)
        *   `air_friction`: `0.1`
        *   `mass`: `0.055`

### Projectile Component

This component defines the core behavior of the projectile.

*   **_enabled**: `1` (Component is active)
*   **lob_min/lob_max**: `0.8`/`1.0` (Controls the arc of the projectile)
*   **speed_min/speed_max**: `100`/`140` (Defines the projectile's speed range)
*   **die_on_low_velocity**: `0` (Does not die if its velocity becomes too low)
*   **on_death_explode**: `1` (Explodes when it dies)
*   **on_death_gfx_leave_sprite**: `0` (Does not leave a sprite graphic upon death)
*   **on_lifetime_out_explode**: `1` (Explodes when its lifetime expires)
*   **explosion_dont_damage_shooter**: `1` (The explosion does not harm the entity that fired it)
*   **damage**: `0.3` (Base damage of the projectile itself)
*   **on_collision_die**: `0` (Does not die upon collision)
*   **lifetime**: `100` (Duration in frames before expiring)
*   **knockback_force**: `2.0` (Force applied to entities it hits)
*   **bounces_left**: `10` (Number of bounces allowed)
*   **bounce_always**: `1` (Always bounces, regardless of surface)

#### Projectile Explosion Configuration (`config_explosion`)

*   **never_cache**: `1`
*   **camera_shake**: `0.5`
*   **explosion_radius**: `18`
*   **explosion_sprite**: `data/particles/explosion_016_plasma.xml`
*   **create_cell_probability**: `1`
*   **create_cell_material**: `plasma_fading`
*   **explosion_sprite_emissive**: `1`
*   **explosion_sprite_additive**: `1`
*   **ray_energy**: `100000`
*   **hole_destroy_liquid**: `1`
*   **hole_enabled**: `1`
*   **damage**: `0.6` (Damage dealt by the explosion)
*   **damage_mortals**: `1` (Explosion damages living entities)
*   **physics_throw_enabled**: `1`
*   **shake_vegetation**: `1`
*   **sparks_enabled**: `1`
*   **spark_material**: `spark_blue`
*   **sparks_count_min/max**: `12`/`16`
*   **light_r/g/b**: `45`/`200`/`250`
*   **stains_enabled**: `1`
*   **stains_image**: `data/temp/explosion_stain.png`

### Sprite Component

Defines the visual appearance of the projectile.

*   **image_file**: `data/projectiles_gfx/orb_blue_big.xml`
*   **rect_animation**: `fireball`
*   **emissive**: `1`
*   **additive**: `1`

### Light Component

Adds a light source to the projectile.

*   **radius**: `150`
*   **r/g/b**: `40`/`185`/`250`

### Particle Emitters

*   **SpriteParticleEmitterComponent**: Emits electric sparks.
    *   `sprite_file`: `data/particles/spark_electric.xml`
    *   `emission_interval_min_frames`/`max_frames`: `3`/`4`
    *   `count_min`/`max`: `1`/`2`
    *   `randomize_rotation.min/max`: `-3.1415`/`3.1415`
    *   `randomize_position.min/max_x/y`: `-8`/`8`
*   **ParticleEmitterComponent**: Emits blue sparks.
    *   `emitted_material_name`: `spark_blue`
    *   `lifetime_min/max`: `0.3`/`0.8`
    *   `count_min/max`: `20`/`30`
    *   `area_circle_radius.min/max`: `1`/`2`
    *   `airflow_force`: `1.5`
    *   `velocity_always_away_from_center`: `180`

### Audio Components

*   **AudioComponent**: Plays a sound event on projectile creation.
    *   `file`: `data/audio/Desktop/projectiles.bank`
    *   `event_root`: `player_projectiles/black_hole`
*   **AudioLoopComponent**: Plays a looping sound.
    *   `file`: `data/audio/Desktop/projectiles.bank`
    *   `event_name`: `projectiles/magic_orb/loop`
    *   `auto_play`: `1`

### Lua Component

*   **script_source_file**: `data/entities/animals/boss_spirit/orb_effect.lua`
    *   `execute_every_n_frame`: `95`
    *   `remove_after_executed`: `1` (The Lua script runs once and then is removed)

### Variable Storage Component

*   **name**: `projectile_file`
*   **value_string**: `data/entities/animals/boss_spirit/orb.xml` (Stores the path to this entity's definition)