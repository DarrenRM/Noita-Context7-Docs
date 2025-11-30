---
title: Big Magic Shield Part Projectile
category: data/entities
---

# Big Magic Shield Part Projectile

This entity defines a projectile that acts as a component of a larger magic shield. It has minimal velocity, emits particles, and possesses an energy shield component.

## Base Projectile Properties

The projectile inherits base properties from `base_projectile.xml`.

### Velocity Component

*   `gravity_y`: `0` - No vertical gravity applied.
*   `air_friction`: `0` - No air friction.

## Projectile Component

This component defines the core behavior of the projectile.

*   `lob_min`, `lob_max`: `0.8`, `1.0` - Controls the lobbing behavior, suggesting a slight upward arc.
*   `speed_min`, `speed_max`: `0`, `0` - The projectile has no initial speed.
*   `die_on_low_velocity`: `0` - Does not die when velocity becomes low.
*   `on_death_explode`: `0` - Does not explode upon death.
*   `on_death_gfx_leave_sprite`: `0` - Does not leave a sprite upon death.
*   `on_lifetime_out_explode`: `0` - Does not explode when lifetime ends.
*   `explosion_dont_damage_shooter`: `1` - The projectile will not damage the shooter if it were to explode (though it doesn't).
*   `penetrate_entities`: `1` - Can pass through entities.
*   `damage`: `0.09` - Deals a small amount of damage.
*   `on_collision_die`: `0` - Does not die on collision.
*   `damage_every_x_frames`: `20` - Deals damage every 20 frames.
*   `lifetime`: `500` - The projectile exists for 500 frames.

## Sprite Component

Defines the visual appearance of the projectile.

*   `image_file`: `data/particles/star.xml` - Uses a star particle sprite.
*   `offset_x`, `offset_y`: `6`, `6` - Offsets the sprite's position.
*   `additive`: `1` - Uses additive blending for the sprite.
*   `rect_animation`: `spawn` - Uses a "spawn" animation.

## Light Component

Adds a light source to the projectile.

*   `radius`: `90` - The radius of the light.
*   `r`, `g`, `b`: `30`, `95`, `160` - Defines the light color (a bluish hue).

## Particle Emitter Components (x2)

These components emit particles to create visual effects.

*   `emitted_material_name`: `plasma_fading` - Emits particles of the "plasma\_fading" material.
*   `gravity.y`: `0.0` - Emitted particles are not affected by gravity.
*   `lifetime_min`, `lifetime_max`: `0.1`, `0.8` - The lifetime of emitted particles.
*   `count_min`, `count_max`: `1`, `1` - Emits a small number of particles.
*   `fade_based_on_lifetime`: `1` - Particles fade as their lifetime decreases.
*   `airflow_force`, `airflow_time`, `airflow_scale`: `0.3`, `0.01`, `0.05` - Apply a slight airflow effect to particles.
*   `emit_cosmetic_particles`: `1` - Emits cosmetic particles.
*   `is_emitting`: `1` - The emitter is active.

## Lua Component

Attaches a Lua script for custom behavior.

*   `script_source_file`: `data/scripts/projectiles/big_magic_shield_part.lua` - The script controlling the projectile's logic.
*   `execute_every_n_frame`: `1` - The script executes every frame.

## Energy Shield Component

This component grants the projectile energy shield properties.

*   `recharge_speed`: `0.25` - The speed at which the shield recharges.
*   `max_energy`: `1.0` - The maximum energy capacity of the shield.
*   `energy`: `1.0` - The initial energy of the shield.
*   `radius`: `8` - The radius of the shield.

## Audio Component

Plays a sound effect when the projectile is active.

*   `file`: `data/audio/Desktop/projectiles.bank` - The audio bank file.
*   `event_root`: `player_projectiles/magic_shield` - The root event for the sound.

## Audio Loop Component

Plays a looping sound effect.

*   `file`: `data/audio/Desktop/projectiles.bank` - The audio bank file.
*   `event_name`: `player_projectiles/magic_shield/loop` - The name of the looping event.
*   `auto_play`: `1` - The sound starts playing automatically.