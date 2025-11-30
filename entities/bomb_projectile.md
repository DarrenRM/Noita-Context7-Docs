---
title: Bomb Projectile
category: entities
---

# Bomb Projectile

This document details the configuration of the Bomb projectile entity in Noita, focusing on its core attributes and behaviors relevant to AI-assisted modding.

## Core Components

### Base Projectile Physics

This component defines the fundamental physics and visual representation of the projectile.

*   **`PhysicsImageShapeComponent`**:
    *   `image_file`: `data/items_gfx/bomb.png` - Specifies the visual sprite for the bomb.
    *   `material`: `fuse` - Defines the material properties, influencing interactions.

### Projectile Component

This is the primary component for defining projectile behavior, including its lifespan, damage, and explosion properties.

*   **`ProjectileComponent`**:
    *   `lifetime`: `180` - The duration in frames before the projectile self-destructs if it doesn't hit anything.
    *   `damage`: `0` - Base damage of the projectile itself (before explosion).
    *   `muzzle_flash_file`: `data/entities/particles/muzzle_flashes/muzzle_flash_launcher_large.xml` - The particle effect used for the muzzle flash when fired.
    *   `shoot_light_flash_radius`: `120` - The radius of the light flash when the projectile is fired.
    *   `shoot_light_flash_r`, `g`, `b`: `255`, `240`, `30` - RGB values for the shooting light flash color (yellowish).

#### `config_explosion` (Nested within `ProjectileComponent`)

This section defines the parameters for the explosion that occurs when the projectile detonates.

*   `never_cache`: `0` - Whether the explosion should be cached.
*   `damage`: `5` - The damage dealt by the explosion.
*   `camera_shake`: `50` - The intensity of camera shake upon explosion.
*   `explosion_radius`: `60` - The radius of the explosion's effect.
*   `explosion_sprite`: `data/particles/explosion_128.xml` - The particle effect used for the visual explosion.
*   `load_this_entity`: `data/entities/particles/particle_explosion/main_gunpowder_large.xml,data/entities/misc/loose_ground.xml,data/entities/misc/explosion_was_here.xml` - Entities to spawn upon explosion (e.g., explosion particles, loose ground, and a marker).
*   `create_cell_probability`: `40` - The percentage chance to create a hole in the environment.
*   `hole_destroy_liquid`: `0` - Whether the explosion should destroy liquids.
*   `hole_enabled`: `1` - Whether hole creation is enabled.
*   `ray_energy`: `6000000` - The energy of the explosion's damaging rays.
*   `particle_effect`: `1` - Whether to spawn particles from the explosion.
*   `damage_mortals`: `1` - Whether the explosion damages living entities.
*   `physics_explosion_power.min`, `.max`: `2.2`, `3.6` - The minimum and maximum force applied to physics objects by the explosion.
*   `physics_throw_enabled`: `1` - Whether the explosion can throw physics objects.
*   `shake_vegetation`: `1` - Whether the explosion shakes vegetation.
*   `sparks_count_min`, `max`: `12`, `15` - The range for the number of sparks spawned.
*   `sparks_enabled`: `1` - Whether sparks are enabled.
*   `stains_enabled`: `1` - Whether explosion stains are enabled.
*   `stains_radius`: `15` - The radius of the explosion stains.
*   `max_durability_to_destroy`: `11` - The maximum durability of objects that can be destroyed by the explosion.

### Physics Throwable Component

This component allows the projectile to be thrown by physics.

*   **`PhysicsThrowableComponent`**:
    *   `_tags`: `enabled_in_world` - Ensures this component is active in the game world.
    *   `throw_force_coeff`: `0.75` - A coefficient affecting the force applied when throwing.

## Visual Effects (FX)

### Particle Emitters

These components define the visual particles that accompany the bomb.

*   **`ParticleEmitterComponent` (Smoke)**:
    *   `emitted_material_name`: `smoke` - Spawns smoke particles.
    *   `count_min`, `max`: `0`, `4` - The number of smoke particles emitted per interval.
    *   `lifetime_min`, `max`: `0.1`, `0.3` - The lifespan of smoke particles.
    *   `is_emitting`: `1` - Enables emission.

*   **`ParticleEmitterComponent` (Cosmetic Sparks)**:
    *   `emitted_material_name`: `spark` - Spawns spark particles.
    *   `create_real_particles`: `0` - These are cosmetic, not physical.
    *   `emit_cosmetic_particles`: `1` - Explicitly marks these as cosmetic.
    *   `count_min`, `max`: `1`, `2` - The number of cosmetic sparks emitted.
    *   `lifetime_min`, `max`: `0.1`, `0.3` - The lifespan of cosmetic sparks.

*   **`ParticleEmitterComponent` (Sparse Trail Sparks)**:
    *   `emitted_material_name`: `spark` - Spawns spark particles.
    *   `x_vel_min`, `max`: `10`, `20` - Defines horizontal velocity for sparks.
    *   `y_vel_min`, `max`: `0`, `0` - No vertical velocity.
    *   `gravity.y`: `0.0` - No gravity applied to these sparks.
    *   `count_min`, `max`: `1`, `1` - Emits one spark at a time.
    *   `lifetime_min`, `max`: `1.4`, `1.5` - Longer lifespan for trail sparks.
    *   `is_trail`: `0` - Not a continuous trail, but discrete sparks.
    *   `emission_interval_min_frames`, `max`: `10`, `30` - Emits sparks infrequently.
    *   `airflow_force`, `time`, `scale`: `0.5`, `0.5`, `0.05` - Applies a subtle airflow effect.

## Audio Components

### Audio Component

Plays a specific sound event when the projectile is fired.

*   **`AudioComponent`**:
    *   `file`: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound.
    *   `event_root`: `player_projectiles/bomb` - The specific sound event for the bomb projectile.

### Audio Loop Component

Plays a continuous sound effect while the projectile is active (e.g., fuse burning).

*   **`AudioLoopComponent`**:
    *   `file`: `data/audio/Desktop/projectiles.bank` - The audio bank.
    *   `event_name`: `projectiles/fuse_burn_slow` - The name of the looping sound event.
    *   `auto_play`: `1` - Starts playing the sound automatically.

## Variable Storage Component

Stores a variable that can be referenced by other game systems.

*   **`VariableStorageComponent`**:
    *   `name`: `projectile_file` - The name of the variable.
    *   `value_string`: `data/entities/projectiles/bomb.xml` - The value, pointing to this entity's file.