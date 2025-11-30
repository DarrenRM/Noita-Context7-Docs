---
title: Super Teleport Cast Projectile
category: entities
---

# Super Teleport Cast Projectile

This entity defines the behavior and appearance of the "Super Teleport Cast" projectile in Noita. It's a player-owned projectile designed for rapid, non-damaging teleportation.

## Key Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile properties.

*   **`gravity_y="0"`**: The projectile is not affected by gravity.
*   **`mass="0.04"`**: A very low mass, contributing to its swift movement.

### Projectile (`<ProjectileComponent>`)

This is the core component defining the projectile's specific mechanics.

*   **`_enabled="1"`**: The component is active.
*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the lobbing behavior, with minimal deviation from a straight path.
*   **`speed_min="100"`, `speed_max="100"`**: The projectile travels at a constant speed of 100 units.
*   **`direction_random_rad="0"`**: No random deviation in direction upon firing.
*   **`on_death_explode="0"`**: Does not explode upon death.
*   **`on_death_gfx_leave_sprite="0"`**: Does not leave a sprite graphic upon death.
*   **`on_lifetime_out_explode="0"`**: Does not explode when its lifetime expires.
*   **`explosion_dont_damage_shooter="1"`**: If it were to explode, it wouldn't damage the shooter.
*   **`on_collision_die="0"`**: Does not die upon collision with entities.
*   **`die_on_liquid_collision="0"`**: Does not die upon collision with liquids.
*   **`lifetime="5"`**: The projectile exists for 5 seconds.
*   **`damage="0"`**: Deals no damage.
*   **`camera_shake_when_shot="5.0"`**: Causes a moderate camera shake when fired.
*   **`penetrate_entities="1"`**: Can pass through multiple entities.
*   **`damage_every_x_frames="25"`**: If damage were applied, it would be every 25 frames (though damage is 0 here).

### Light (`<LightComponent>`)

This component adds a visual light effect to the projectile.

*   **`_enabled="1"`**: The light component is active.
*   **`radius="20"`**: The radius of the light effect.
*   **`r="30"`, `g="90"`, `b="30"`**: Defines the greenish color of the light.

### Particle Emitter (`<ParticleEmitterComponent>`)

This component generates cosmetic particles to enhance the visual trail of the projectile.

*   **`emitted_material_name="spark_purple_bright"`**: The type of particle emitted.
*   **`gravity.y="0.0"`**: Particles are not affected by gravity.
*   **`x_vel_min="-20"`, `x_vel_max="20"`, `y_vel_min="-20"`, `y_vel_max="20"`**: Particles have a random velocity within this range.
*   **`count_min="1"`, `count_max="1"`**: Emits one particle per emission.
*   **`lifetime_min="0.65"`, `lifetime_max="1.2"`**: Particles last between 0.65 and 1.2 seconds.
*   **`emit_real_particles="0"`**: Emits cosmetic particles, not physics-affecting ones.
*   **`render_on_grid="1"`**: Particles are rendered on the game grid.
*   **`airflow_force="0.3"`, `airflow_time="0.01"`, `airflow_scale="0.05"`**: Minor airflow effects on particles.
*   **`emit_cosmetic_particles="1"`**: Explicitly emits cosmetic particles.
*   **`emission_interval_min_frames="1"`, `emission_interval_max_frames="2"`**: Particles are emitted frequently, every 1-2 frames.
*   **`area_circle_radius.max="4"`**: Particles are emitted within a small circular area.
*   **`fade_based_on_lifetime="1"`**: Particles fade out as their lifetime ends.
*   **`is_trail="1"`**: This emitter is designed to create a trail effect.
*   **`trail_gap="0.5"`**: The gap between trail particles.
*   **`is_emitting="1"`**: The emitter is active.

### Lua Component (`<LuaComponent>`)

This component executes custom Lua script for advanced functionality.

*   **`script_source_file="data/scripts/projectiles/super_teleport_cast.lua"`**: Points to the external Lua script that handles the projectile's logic.
*   **`execute_every_n_frame="2"`**: The script runs every 2 frames.
*   **`remove_after_executed="1"`**: The Lua component is removed after its first execution. This implies the script itself manages any ongoing effects or logic.