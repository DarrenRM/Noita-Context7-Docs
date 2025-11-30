---
title: Propane Tank Projectile
category: entities
---

# Propane Tank Projectile

This document details the configuration of the Propane Tank projectile entity in Noita, focusing on its behavior, appearance, and explosive properties.

## Core Components

The propane tank projectile is built upon several base components that define its fundamental characteristics.

### Base Projectile Physics

*   **`projectiles_rotate_toward_velocity`**: `1` - The projectile will orient itself to face its direction of movement.
*   **`hax_fix_going_through_ground`**: `0` - Disables a specific fix for projectiles passing through the ground.

### Physics Image Shape

*   **`image_file`**: `data/props_gfx/propane_tank_horizontal.png` - Specifies the visual sprite for the propane tank.
*   **`material`**: `steel` - Defines the physical material properties of the tank.

### Projectile Component

This component governs the projectile's lifespan, damage, and explosion effects.

*   **`lifetime`**: `-1` - The projectile does not have a set lifespan and will persist until other conditions are met.
*   **`damage`**: `0` - The projectile itself deals no direct damage upon impact.
*   **`muzzle_flash_file`**: `data/entities/particles/muzzle_flashes/muzzle_flash_launcher_large.xml` - The particle effect used for the muzzle flash when fired.
*   **`shoot_light_flash_radius`**: `120`
*   **`shoot_light_flash_r`**: `255`
*   **`shoot_light_flash_g`**: `240`
*   **`shoot_light_flash_b`**: `30` - Defines the color and intensity of the light flash upon firing.

#### `config_explosion` (within `ProjectileComponent`)

This nested configuration defines the parameters of the explosion that occurs when the projectile detonates.

| Attribute                 | Value                                         | Description                                                                 |
| :------------------------ | :-------------------------------------------- | :-------------------------------------------------------------------------- |
| `never_cache`             | `0`                                           | Allows caching of explosion data.                                           |
| `damage`                  | `13`                                          | The base damage dealt by the explosion.                                     |
| `camera_shake`            | `60`                                          | The intensity of camera shake caused by the explosion.                      |
| `explosion_radius`        | `60`                                          | The radius of the explosion's effect.                                       |
| `explosion_sprite`        | `data/particles/explosion_032.xml`            | The particle effect used for the main explosion visual.                     |
| `explosion_sprite_lifetime` | `10`                                          | The duration (in frames) the explosion sprite is visible.                   |
| `create_cell_probability` | `40`                                          | The chance (in percent) of creating new cells upon explosion.               |
| `create_cell_material`    | `blood_cold_vapour`                           | The material of the cells created by the explosion.                         |
| `hole_destroy_liquid`     | `0`                                           | Whether the explosion should destroy liquids.                               |
| `load_this_entity`        | `data/entities/particles/particle_explosion/main_bluesmoke.xml` | The entity to load for secondary explosion effects (e.g., smoke).           |
| `hole_enabled`            | `1`                                           | Enables the creation of holes in terrain by the explosion.                  |
| `ray_energy`              | `2000000`                                     | The energy value associated with the explosion's raycasting effects.        |
| `particle_effect`         | `1`                                           | Enables particle effects for the explosion.                                 |
| `damage_mortals`          | `1`                                           | The explosion will damage living entities.                                  |
| `physics_explosion_power.min` | `2.5`                                         | Minimum physics force applied to objects by the explosion.                  |
| `physics_explosion_power.max` | `3.5`                                         | Maximum physics force applied to objects by the explosion.                  |
| `physics_throw_enabled`   | `1`                                           | Objects affected by the explosion can be thrown.                            |
| `shake_vegetation`        | `1`                                           | The explosion will shake nearby vegetation.                                 |
| `sparks_count_min`        | `15`                                          | Minimum number of sparks created by the explosion.                          |
| `sparks_count_max`        | `20`                                          | Maximum number of sparks created by the explosion.                          |
| `spark_material`          | `plasma_fading`                               | The material of the sparks.                                                 |
| `sparks_enabled`          | `1`                                           | Enables the creation of sparks.                                             |
| `stains_enabled`          | `1`                                           | Enables the creation of impact stains.                                      |
| `stains_radius`           | `15`                                          | The radius of the impact stains.                                            |
| `delay.min`               | `1`                                           | Minimum delay (in frames) before the explosion occurs.                      |
| `delay.max`               | `4`                                           | Maximum delay (in frames) before the explosion occurs.                      |
| `explosion_delay_id`      | `1`                                           | Identifier for explosion delay synchronization.                             |
| `audio_event_name`        | `explosions/propane_tank`                     | The sound event triggered by the explosion.                                 |

### Damage Model Component

This component defines the tank's durability and how it reacts to damage.

*   **`hp`**: `2` - The hit points of the propane tank.
*   **`falling_damage_damage_max`**: `1.2`
*   **`falling_damage_damage_min`**: `0.1`
*   **`falling_damage_height_max`**: `250`
*   **`falling_damage_height_min`**: `70`
*   **`falling_damages`**: `0` - Falling damage is not enabled for this projectile.
*   **`fire_damage_amount`**: `0.2`
*   **`fire_probability_of_ignition`**: `0` - The tank cannot ignite from fire.
*   **`critical_damage_resistance`**: `1`
*   **`materials_create_messages`**: `0`
*   **`materials_damage`**: `0`
*   **`is_on_fire`**: `0`

### Physics Throwable Component

This component allows the projectile to be thrown.

*   **`_tags`**: `enabled_in_world` - The component is active when the entity is in the game world.
*   **`attach_to_surfaces_knife_style`**: `0`
*   **`throw_force_coeff`**: `0.75` - The coefficient determining the force applied when throwing.

## Material Inventory Component

This component manages the "contents" of the propane tank, which are released upon damage or death.

*   **`drop_as_item`**: `0` - The tank does not drop as a usable item upon death.
*   **`on_death_spill`**: `1` - The contents will spill out when the tank is destroyed.
*   **`leak_on_damage_percent`**: `0.999` - The tank will start leaking when it reaches 99.9% damage.
*   **`b2_force_on_leak`**: `0.6` - The force applied to the spilled material.
*   **`kill_when_empty`**: `1` - The tank entity is destroyed when its contents are depleted.

### `count_per_material_type`

*   **`Material material="blood_cold_vapour" count="300"`**: The tank contains 300 units of `blood_cold_vapour` material.

## Particle Emitter Component

This component is responsible for emitting particles, likely representing the leaking gas or vapor.

*   **`_enabled`**: `1` - The emitter is active.
*   **`collide_with_gas_and_fire`**: `1` - Particles can interact with gas and fire.
*   **`collide_with_grid`**: `1` - Particles can interact with the game grid.
*   **`cosmetic_force_create`**: `1` - Creates cosmetic particles.
*   **`count_max`**: `1`
*   **`count_min`**: `1` - Emits a single particle at a time.
*   **`create_real_particles`**: `0` - Does not create "real" physics particles.
*   **`emission_chance`**: `100` - Always emits particles when active.
*   **`emission_interval_max_frames`**: `2`
*   **`emission_interval_min_frames`**: `1` - Emits particles every 1-2 frames.
*   **`emit_real_particles`**: `1` - Emits actual particles.
*   **`emitted_material_name`**: `blood` - The material of the emitted particles (though the `create_cell_material` in the explosion is `blood_cold_vapour`, suggesting a potential discrepancy or specific behavior).
*   **`lifetime_max`**: `10`
*   **`lifetime_min`**: `5` - Particles last between 5 and 10 frames.
*   **`offset.x`**: `-8.5` - Offset from the projectile's center.
*   **`x_vel_max`**: `-150.1366`
*   **`x_vel_min`**: `-125.4561` - Particles are emitted with a negative X velocity, pushing them away from the projectile.
*   **`gravity.y`**: `200` - Particles are affected by gravity.

## Explode On Damage Component

This component dictates when and how the projectile explodes in response to damage.

*   **`explode_on_death_percent`**: `1.0` - The projectile will explode when it reaches 100% damage (death).
*   **`explode_on_damage_percent`**: `0.0` - The projectile will not explode solely based on a damage percentage threshold (other conditions must be met).
*   **`physics_body_modified_death_probability`**: `1.0` - If the physics body is modified upon death, it will always explode.
*   **`physics_body_destruction_required`**: `0.3` - The physics body needs to be at least 30% destroyed for an explosion to be considered.

The `config_explosion` within this component is identical to the one within the `ProjectileComponent`, ensuring consistent explosion behavior.

## Audio Components

### Audio Loop Component

*   **`_tags`**: `sound_spray`
*   **`file`**: `data/audio/Desktop/materials.bank`
*   **`event_name`**: `materials/spray`
*   **`volume_autofade_speed`**: `0.25` - Likely related to a spraying sound effect.

### Audio Component

*   **`file`**: `data/audio/Desktop/projectiles.bank`
*   **`event_root`**: `player_projectiles/propane_tank` - Defines the sound event for the propane tank projectile.

## Variable Storage Component

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/projectiles/propane_tank.xml` - Stores the path to this entity's XML file.