---
title: Teleport Cast Projectile
category: entities
---

# Teleport Cast Projectile

This document describes the `teleport_cast.xml` entity, which defines the behavior and appearance of the Teleport Cast projectile in Noita. This projectile is primarily used by the player and has unique teleportation properties.

## Entity Definition

The core of the entity is defined by the `<Entity>` tag.

```xml
<Entity 
  name="$projectile_default" tags="projectile_player"
   >
  ...
</Entity>
```

-   **`name="$projectile_default"`**: This indicates it uses a default projectile name, likely to be overridden by specific spell configurations.
-   **`tags="projectile_player"`**: This tag identifies the projectile as originating from the player.

## Base Projectile Properties

The `<Base>` tag inherits properties from `data/entities/base_projectile.xml`.

```xml
<Base file="data/entities/base_projectile.xml" >
    <VelocityComponent
        gravity_y="0"
        mass="0.04"
    >
    </VelocityComponent>
</Base>
```

-   **`gravity_y="0"`**: The projectile is not affected by gravity, allowing for straight-line travel or custom trajectories.
-   **`mass="0.04"`**: A small mass value, contributing to its projectile behavior.

## Projectile Component

This component defines the specific behaviors of the Teleport Cast projectile.

```xml
<ProjectileComponent 
    _enabled="1" 
    lob_min="0.8"
    lob_max="1.0"
    speed_min="26"
    speed_max="26"
    direction_random_rad="0"
    on_death_explode="0"
    on_death_gfx_leave_sprite="0" 
    on_lifetime_out_explode="0"
    explosion_dont_damage_shooter="1" 
    on_collision_die="0"
	die_on_liquid_collision="0"
    lifetime="2"
    damage="0"
    ragdoll_force_multiplier="0.0"
    hit_particle_force_multiplier="0.0"
    camera_shake_when_shot="5.0"
    bounces_left="0"
	muzzle_flash_file=""
	shoot_light_flash_radius="1"
	knockback_force="0"
	physics_impulse_coeff="0"
	penetrate_entities="1"
	damage_every_x_frames="25"
	>
    <config_explosion 
		damage="0"
		radius="1"
		>
	</config_explosion>
</ProjectileComponent>
```

**Key Attributes:**

-   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the arc of the projectile. Values close to 1 suggest a relatively straight trajectory.
-   **`speed_min="26"`, `speed_max="26"`**: The projectile travels at a fixed speed of 26 units per frame.
-   **`direction_random_rad="0"`**: No randomness in the projectile's initial direction.
-   **`on_death_explode="0"`, `on_lifetime_out_explode="0"`**: The projectile does not explode upon death or when its lifetime expires.
-   **`on_collision_die="0"`, `die_on_liquid_collision="0"`**: The projectile does not die upon colliding with entities or liquids.
-   **`lifetime="2"`**: The projectile exists for 2 seconds.
-   **`damage="0"`**: This projectile deals no direct damage.
-   **`camera_shake_when_shot="5.0"`**: Causes a camera shake of magnitude 5.0 when the projectile is fired.
-   **`penetrate_entities="1"`**: The projectile can pass through multiple entities without dying.
-   **`config_explosion`**: Defines explosion properties, but with `damage="0"` and `radius="1"`, it has no significant impact.

## Light Component

This component adds a light source to the projectile.

```xml
<LightComponent 
    _enabled="1" 
    radius="20" 
    r="30"
    g="90"
    b="30">
</LightComponent>
```

-   **`radius="20"`**: The light extends to a radius of 20 units.
-   **`r="30"`, `g="90"`, `b="30"`**: The light color is a greenish hue.

## Particle Emitter Component

This component defines the visual particles emitted by the projectile.

```xml
<ParticleEmitterComponent 
    emitted_material_name="plasma_fading_green"
    offset.x="0"
    offset.y="0"
	gravity.y="0.0"
	x_vel_min="-20"
    x_vel_max="20"
    y_vel_min="-20"
    y_vel_max="20"
    count_min="1"
    count_max="1"
    lifetime_min="0.65"
    lifetime_max="1.2"
    emit_real_particles="0"
	render_on_grid="1"
	airflow_force="0.3"
	airflow_time="0.01"
	airflow_scale="0.05"
    emit_cosmetic_particles="1"
    emission_interval_min_frames="1"
    emission_interval_max_frames="2"
	area_circle_radius.max="4"
	fade_based_on_lifetime="1"
    is_emitting="1" >
</ParticleEmitterComponent>
```

**Key Attributes:**

-   **`emitted_material_name="plasma_fading_green"`**: The particles are of the "plasma\_fading\_green" material.
-   **`gravity.y="0.0"`**: Particles are not affected by gravity.
-   **`x_vel_min/max`, `y_vel_min/max`**: Particles are emitted with a velocity range, creating a spread effect.
-   **`lifetime_min/max`**: Particles have a lifespan between 0.65 and 1.2 seconds.
-   **`emit_cosmetic_particles="1"`**: These are cosmetic particles, meaning they don't affect gameplay mechanics directly.
-   **`area_circle_radius.max="4"`**: Particles are emitted within a small circular area.
-   **`is_emitting="1"`**: The particle emitter is active.

## Lua Component

This component links the projectile to a Lua script for custom logic.

```xml
<LuaComponent
	script_source_file="data/scripts/projectiles/teleport_cast.lua"
	execute_on_added="1"
	remove_after_executed="1"
	>
</LuaComponent>
```

-   **`script_source_file="data/scripts/projectiles/teleport_cast.lua"`**: This is the crucial part, indicating that the `teleport_cast.lua` script handles the unique teleportation behavior of this projectile.
-   **`execute_on_added="1"`**: The script will execute as soon as the projectile is added to the game world.
-   **`remove_after_executed="1"`**: The Lua component will be removed after its script has executed once.