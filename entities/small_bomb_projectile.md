---
title: Small Bomb Projectile
category: entities
---

# Small Bomb Projectile

This document details the configuration of the `bomb_small.xml` entity, representing a small bomb projectile in Noita. It focuses on key attributes that define its behavior, appearance, and effects.

## Base Entity Configuration

The projectile inherits its core physics and behavior from `data/entities/base_projectile_physics.xml`.

### PhysicsImageShapeComponent

Defines the visual representation and physical material of the projectile.

*   **`image_file`**: `data/items_gfx/bomb.png` - Specifies the sprite used for the bomb.
*   **`material`**: `fuse` - The material type, influencing its interaction with the environment.

### ProjectileComponent

Governs the projectile's lifespan, visual effects upon firing, and its explosion properties.

*   **`lifetime`**: `260` - The duration in frames before the projectile self-destructs if it doesn't hit anything.
*   **`muzzle_flash_file`**: `data/entities/particles/muzzle_flashes/muzzle_flash_launcher_large.xml` - The particle effect used when the projectile is fired.
*   **`shoot_light_flash_radius`**: `120` - The radius of the light flash emitted upon firing.
*   **`shoot_light_flash_r`, `shoot_light_flash_g`, `shoot_light_flash_b`**: `255`, `240`, `30` - RGB values for the light flash color (yellowish).

#### `config_explosion`

Defines the parameters of the explosion when the projectile detonates.

*   **`damage`**: `5` - The base damage dealt by the explosion.
*   **`camera_shake`**: `50` - The intensity of camera shake experienced by players near the explosion.
*   **`explosion_radius`**: `40` - The area of effect for the explosion.
*   **`explosion_sprite`**: `data/particles/explosion_128.xml` - The sprite used for the main explosion visual.
*   **`load_this_entity`**: `data/entities/particles/particle_explosion/main_large_radius.xml,data/entities/misc/loose_ground.xml` - Entities to spawn upon explosion, including larger explosion effects and loose ground.
*   **`create_cell_probability`**: `40` - The chance (in percent) to create destructible terrain cells.
*   **`hole_enabled`**: `1` - Enables the creation of holes in terrain.
*   **`ray_energy`**: `6000000` - The energy value associated with the explosion's destructive rays.
*   **`particle_effect`**: `1` - Enables the spawning of explosion particles.
*   **`damage_mortals`**: `1` - The explosion deals damage to living entities.
*   **`physics_explosion_power.min` / `.max`**: `2.2` / `3.6` - The minimum and maximum force applied to physics objects by the explosion.
*   **`physics_throw_enabled`**: `1` - Physics objects can be thrown by the explosion.
*   **`shake_vegetation`**: `1` - Causes vegetation to shake from the explosion.
*   **`sparks_count_min` / `max`**: `12` / `15` - The range for the number of sparks spawned.
*   **`stains_enabled`**: `1` - Enables the creation of explosion stains on surfaces.
*   **`stains_radius`**: `15` - The radius of the explosion stains.
*   **`max_durability_to_destroy`**: `11` - The maximum durability of an object that can be destroyed by this explosion.

### PhysicsThrowableComponent

Enables the projectile to be thrown with a certain force.

*   **`_tags`**: `enabled_in_world` - The component is active when the entity is in the game world.
*   **`throw_force_coeff`**: `0.75` - A coefficient affecting the force applied when throwing.

## Visual Effects (Particle Emitters)

The bomb emits various particles to simulate smoke and sparks.

### Smoke Emitter

*   **`emitted_material_name`**: `smoke` - Spawns smoke particles.
*   **`count_min` / `max`**: `0` / `4` - The number of smoke particles emitted per interval.
*   **`lifetime_min` / `max`**: `0.1` / `0.3` - The lifespan of individual smoke particles.
*   **`is_emitting`**: `1` - The emitter is active.

### Cosmetic Spark Emitter

*   **`emitted_material_name`**: `spark` - Spawns spark particles.
*   **`create_real_particles`**: `0` - These are cosmetic particles, not affecting gameplay physics.
*   **`emit_cosmetic_particles`**: `1` - Explicitly marks these as cosmetic.
*   **`count_min` / `max`**: `1` / `2` - The number of cosmetic sparks emitted per interval.
*   **`lifetime_min` / `max`**: `0.1` / `0.3` - The lifespan of individual cosmetic sparks.

### Sparse Trail Spark Emitter

*   **`emitted_material_name`**: `spark` - Spawns spark particles.
*   **`x_vel_min` / `max`**: `10` / `20` - Sparks are primarily propelled horizontally.
*   **`y_vel_min` / `max`**: `0` / `0` - No vertical velocity initially.
*   **`gravity.y`**: `0.0` - No gravity applied to these sparks.
*   **`count_min` / `max`**: `1` / `1` - A single spark is emitted per interval.
*   **`lifetime_min` / `max`**: `1.4` / `1.5` - These sparks have a longer lifespan.
*   **`is_trail`**: `0` - Not a continuous trail.
*   **`render_on_grid`**: `1` - Renders even on the grid.
*   **`emission_interval_min_frames` / `max_frames`**: `10` / `30` - Emits sparks infrequently.
*   **`emit_cosmetic_particles`**: `1` - These are cosmetic sparks.

## Audio Components

Defines the sound effects associated with the bomb.

### AudioComponent

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing projectile sounds.
*   **`event_root`**: `player_projectiles/bomb` - The base event for bomb projectile sounds.

### AudioLoopComponent

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank.
*   **`event_name`**: `projectiles/fuse_burn_slow` - The specific sound event for the fuse burning.
*   **`auto_play`**: `1` - The sound starts playing automatically.

## Variable Storage

Stores a reference to the projectile's own entity file.

### VariableStorageComponent

*   **`name`**: `projectile_file` - The name of the variable.
*   **`value_string`**: `data/entities/projectiles/bomb_small.xml` - The value, pointing to this entity's XML file.