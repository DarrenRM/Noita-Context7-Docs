---
title: Dot Shot Strong Projectile
category: entities
---

# Dot Shot Strong Projectile

This document details the configuration of the `dotshot_strong.xml` projectile entity in Noita, focusing on its key attributes for AI-assisted modding.

## Base Projectile Configuration

The projectile inherits fundamental properties from `base_projectile.xml`.

### Velocity Component

*   **`gravity_y`**: `0` - The projectile is not affected by gravity.
*   **`air_friction`**: `-2` - A negative value indicates acceleration in air, rather than deceleration.
*   **`mass`**: `0.05` - Defines the projectile's mass.

## Projectile Component

This component governs the projectile's behavior and effects.

### Key Attributes

*   **`lob_min` / `lob_max`**: `0.8` / `1.0` - Controls the minimum and maximum lobbing behavior (arc of trajectory).
*   **`speed_min` / `speed_max`**: `150` - The projectile travels at a constant speed of 150 units.
*   **`die_on_low_velocity`**: `0` - The projectile does not disappear if its velocity drops too low.
*   **`on_death_explode`**: `1` - The projectile explodes upon death.
*   **`on_lifetime_out_explode`**: `1` - The projectile explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter`**: `1` - The explosion does not harm the entity that fired the projectile.
*   **`damage`**: `0.8` - The base damage dealt by the projectile.
*   **`on_collision_die`**: `1` - The projectile is destroyed upon collision.
*   **`lifetime`**: `100` - The projectile exists for 100 frames before expiring.
*   **`knockback_force`**: `1.0` - The force applied to entities upon being hit.

### Explosion Configuration (`config_explosion`)

*   **`never_cache`**: `1` - Ensures the explosion is always generated fresh.
*   **`camera_shake`**: `0` - No camera shake is applied on explosion.
*   **`explosion_radius`**: `10` - The radius of the explosion effect.
*   **`explosion_sprite`**: `data/particles/explosion_016_plasma_pink.xml` - The visual effect used for the explosion.
*   **`ray_energy`**: `5000` - The energy value associated with the explosion's ray effects.
*   **`hole_enabled`**: `1` - Creates a hole in the environment upon explosion.
*   **`hole_image`**: `data/temp/explosion_hole.png` - The texture used for the explosion hole.
*   **`explosion_sprite_emissive`**: `1` - The explosion sprite is emissive.
*   **`explosion_sprite_additive`**: `1` - The explosion sprite uses additive blending.
*   **`physics_explosion_power.min` / `.max`**: `0.24` / `0.34` - The minimum and maximum power of the physics-based explosion.
*   **`physics_throw_enabled`**: `1` - The explosion can throw nearby objects.
*   **`shake_vegetation`**: `1` - The explosion will shake vegetation.
*   **`light_r` / `g` / `b`**: `60` / `10` / `10` - The RGB values for the light emitted by the explosion.

## Sprite Component

Defines the visual appearance of the projectile.

*   **`image_file`**: `data/particles/skullface_red.xml` - The sprite used for the projectile.
*   **`alpha`**: `0.5` - The transparency of the sprite.
*   **`additive`**: `1` - Uses additive blending for the sprite.
*   **`emissive`**: `1` - The sprite is emissive.

## Particle Emitter Component

Controls the emission of cosmetic particles.

*   **`emitted_material_name`**: `spark_red` - The material of the emitted particles.
*   **`is_trail`**: `1` - The particles form a trail.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime decreases.
*   **`emit_cosmetic_particles`**: `1` - Emits cosmetic particles.
*   **`emission_interval_min_frames` / `max_frames`**: `5` / `10` - Controls the frame interval between particle emissions.

## Light Component

Adds a light source to the projectile.

*   **`radius`**: `150` - The radius of the light.
*   **`r` / `g` / `b`**: `90` / `30` / `30` - The RGB values for the light color.

## Audio Component

Defines the sound effects associated with the projectile.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank file.
*   **`event_root`**: `projectiles/orb_b` - The root event for projectile sounds.

## Hit Effect Component

Specifies effects that occur when the projectile hits something.

*   **`effect_hit`**: `LOAD_CHILD_ENTITY` - Loads another entity as a hit effect.
*   **`value_string`**: `data/entities/misc/curse_stronger_init.xml` - The entity to load as the hit effect.