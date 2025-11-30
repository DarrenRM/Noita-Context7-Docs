---
title: Bomb Detonator Projectile
category: entities
---

# Bomb Detonator Projectile

This document details the `bomb_detonator.xml` entity, which defines a special projectile in Noita. This projectile acts as a detonator for other bombs and has unique properties related to its behavior and visual effects.

## Key Attributes

The `bomb_detonator.xml` file defines an entity with the following key components and attributes:

### Entity Definition

*   **`name`**: `$projectile_default` - Indicates this entity inherits default projectile properties.
*   **`tags`**: `projectile_player` - Marks this projectile as originating from the player.

### Base Projectile (`<Base>`)

*   **`file`**: `data/entities/base_projectile.xml` - Inherits core projectile functionality.
    *   **`VelocityComponent`**:
        *   **`gravity_y`**: `0` - The projectile is not affected by gravity.
        *   **`mass`**: `0.04` - Defines the projectile's mass.

### Projectile Component (`<ProjectileComponent>`)

This component governs the projectile's specific behavior.

*   **`_enabled`**: `1` - Ensures the component is active.
*   **`lob_min` / `lob_max`**: `0.8` / `1.0` - Controls the minimum and maximum lob angle, influencing its trajectory.
*   **`speed_min` / `speed_max`**: `26` / `26` - Sets a fixed projectile speed.
*   **`direction_random_rad`**: `0` - The projectile travels in a precise direction without random deviation.
*   **`on_death_explode`**: `0` - The projectile does not explode upon death.
*   **`on_death_gfx_leave_sprite`**: `0` - No sprite is left behind when the projectile dies.
*   **`on_lifetime_out_explode`**: `0` - The projectile does not explode when its lifetime expires.
*   **`explosion_dont_damage_shooter`**: `1` - The projectile's explosion (if any) will not harm the player who shot it.
*   **`on_collision_die`**: `0` - The projectile does not die upon collision with entities.
*   **`die_on_liquid_collision`**: `0` - The projectile does not die when colliding with liquids.
*   **`lifetime`**: `3` - The projectile exists for 3 seconds before expiring.
*   **`damage`**: `0` - The projectile itself deals no damage.
*   **`camera_shake_when_shot`**: `5.0` - Triggers a significant camera shake when this projectile is fired.
*   **`penetrate_entities`**: `1` - The projectile can pass through multiple entities.
*   **`config_explosion`**: An empty tag, indicating no specific explosion configuration is applied directly here.

### Light Component (`<LightComponent>`)

This component adds a light source to the projectile.

*   **`_enabled`**: `1` - The light component is active.
*   **`radius`**: `20` - The radius of the light emitted.
*   **`r` / `g` / `b`**: `255` / `90` / `30` - Defines the light color as a reddish-orange.

### Particle Emitter Component (`<ParticleEmitterComponent>`)

This component generates cosmetic particles around the projectile.

*   **`emitted_material_name`**: `spark` - The type of material used for emitted particles.
*   **`gravity.y`**: `0.0` - Emitted particles are not affected by gravity.
*   **`x_vel_min` / `x_vel_max`**: `-20` / `20` - Sets the horizontal velocity range for particles.
*   **`y_vel_min` / `y_vel_max`**: `-20` / `20` - Sets the vertical velocity range for particles.
*   **`count_min` / `count_max`**: `1` / `1` - A single particle is emitted per emission cycle.
*   **`lifetime_min` / `lifetime_max`**: `0.65` / `1.2` - The duration particles exist.
*   **`emit_real_particles`**: `0` - Emits cosmetic particles, not actual game entities.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`airflow_force` / `airflow_time` / `airflow_scale`**: `0.3` / `0.01` / `0.05` - Parameters influencing how particles interact with airflow.
*   **`emit_cosmetic_particles`**: `1` - Explicitly enables cosmetic particle emission.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `1` / `2` - Particles are emitted frequently, every 1-2 frames.
*   **`area_circle_radius.max`**: `4` - Particles are emitted within a small circular area.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime decreases.
*   **`is_emitting`**: `1` - The particle emitter is active.

### Lua Component (`<LuaComponent>`)

This component allows for custom scripting to control the projectile's behavior.

*   **`script_source_file`**: `data/scripts/projectiles/bomb_detonator.lua` - Specifies the Lua script file that governs this projectile's advanced logic.
*   **`execute_every_n_frame`**: `1` - The Lua script runs every frame.
*   **`remove_after_executed`**: `1` - The Lua script is executed only once and then removed.

This setup suggests that the `bomb_detonator.lua` script handles the primary logic for this projectile, likely involving its interaction with other bombs to trigger their detonation. The XML defines its visual and basic physical properties.