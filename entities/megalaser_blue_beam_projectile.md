---
title: Megalaser Blue Beam Projectile
category: entities
---

# Megalaser Blue Beam Projectile

This document details the configuration for the "megalaser_blue_beam" projectile entity in Noita, focusing on its behavior, visual representation, and particle effects.

## Core Entity Configuration

The `Entity` tag defines the fundamental properties of the projectile.

```xml
<Entity 
	name="$projectile_default" tags="megalaser_beam"
	>
	<!-- ... other components ... -->
</Entity>
```

*   **`name`**: Set to "$projectile_default", indicating it uses a default projectile naming convention.
*   **`tags`**: "megalaser_beam" - This tag is crucial for identifying and potentially interacting with this specific projectile type.

## Base Projectile Properties

The `Base` component inherits common projectile functionalities.

```xml
<Base file="data/entities/base_projectile.xml" >
	<VelocityComponent
		_enabled="1"
		air_friction="-20"
		gravity_y="0"
		mass="0.04"
		>
	</VelocityComponent> 
</Base>
```

*   **`VelocityComponent`**:
    *   `air_friction`: "-20" - A high negative value suggests it's not significantly affected by air resistance, maintaining its velocity.
    *   `gravity_y`: "0" - The projectile is not affected by gravity.
    *   `mass`: "0.04" - A very low mass, contributing to its speed and responsiveness.

## Projectile Behavior (`ProjectileComponent`)

This component governs the projectile's movement, collision, and death effects.

```xml
<ProjectileComponent 
	lob_min="0.8"
	lob_max="1.0"
	speed_min="40"
	speed_max="40"
	die_on_liquid_collision="1"
	on_death_explode="1"
	on_death_gfx_leave_sprite="0" 
	on_lifetime_out_explode="1"
	explosion_dont_damage_shooter="1" 
	on_collision_die="1"
	friendly_fire="0"
	dont_collide_with_tag="drone_lasership"
	shoot_light_flash_radius="15"
	shoot_light_flash_r="80"
	shoot_light_flash_g="80"
	shoot_light_flash_b="255"
	velocity_sets_scale="1"
	damage="0.1"
	lifetime="180"
	penetrate_entities="0"
	hit_particle_force_multiplier="0.25"
	knockback_force="1.5"
	bounces_left="10"
	ragdoll_force_multiplier="0.01"
	ragdoll_fx_on_collision="BLOOD_SPRAY"
	physics_impulse_coeff="5000"
	>
	<!-- ... config_explosion ... -->
</ProjectileComponent>
```

### Key Attributes:

*   **`speed_min`/`speed_max`**: "40" - The projectile travels at a constant speed of 40.
*   **`die_on_liquid_collision`**: "1" - The projectile is destroyed upon contact with liquids.
*   **`on_death_explode`**: "1" - The projectile explodes when it dies.
*   **`on_lifetime_out_explode`**: "1" - The projectile explodes when its lifetime expires.
*   **`on_collision_die`**: "1" - The projectile is destroyed upon colliding with entities.
*   **`friendly_fire`**: "0" - The projectile does not damage the entity that fired it.
*   **`dont_collide_with_tag`**: "drone_lasership" - The projectile will not collide with entities tagged "drone_lasership".
*   **`shoot_light_flash_radius`/`r`/`g`/`b`**: Defines a blue light flash effect when the projectile is fired.
*   **`damage`**: "0.1" - Deals minimal direct damage.
*   **`lifetime`**: "180" - The projectile exists for 180 frames before expiring.
*   **`penetrate_entities`**: "0" - The projectile stops upon hitting an entity.
*   **`knockback_force`**: "1.5" - Applies a moderate knockback effect.
*   **`bounces_left`**: "10" - The projectile can bounce up to 10 times.

### Explosion Configuration (`config_explosion`)

Details the effects when the projectile explodes.

```xml
<config_explosion
	never_cache="1" 
	camera_shake="4.5" 
	explosion_radius="3"
	explosion_sprite="data/particles/explosion_016_plasma.xml" 
	create_cell_material="plasma_fading_bright"
	create_cell_probability="15" 
	hole_enabled="1"
	ray_energy="100000"
	damage="0.05"
	hole_image="data/temp/explosion_hole.png" 
	damage_mortals="1" 
	physics_explosion_power.min="0.2" 
	physics_explosion_power.max="0.35" 
	physics_throw_enabled="1" 
	shake_vegetation="1" 
	stains_enabled="1"
	stains_radius="4" 
	light_fade_time="0.2"
	light_r="10"
	light_g="30"
	light_b="10">
</config_explosion>
```

*   **`camera_shake`**: "4.5" - Causes significant camera shake upon explosion.
*   **`explosion_radius`**: "3" - The radius of the explosion effect.
*   **`explosion_sprite`**: "data/particles/explosion_016_plasma.xml" - Uses a plasma explosion sprite.
*   **`create_cell_material`**: "plasma_fading_bright" - Creates bright, fading plasma cells.
*   **`ray_energy`**: "100000" - A very high value, indicating a powerful energy-based explosion.
*   **`damage`**: "0.05" - Deals minimal damage from the explosion itself.
*   **`hole_enabled`**: "1" - Creates holes in the environment.
*   **`physics_explosion_power.min`/`max`**: "0.2" to "0.35" - Applies physics-based force to the environment.
*   **`shake_vegetation`**: "1" - Causes vegetation to shake.
*   **`stains_enabled`**: "1" - Leaves stains on surfaces.

## Visual Representation (`SpriteComponent`)

Defines the projectile's visual appearance.

```xml
<SpriteComponent 
	_enabled="1"
	emissive="0"
	image_file="data/projectiles_gfx/laser_big.xml" 
	>
</SpriteComponent>
```

*   **`image_file`**: "data/projectiles_gfx/laser_big.xml" - Uses a large laser graphic.

## Particle Effects (`ParticleEmitterComponent`)

These components generate visual particle effects associated with the projectile.

### Solid Particle Line

This emitter creates a continuous trail of particles.

```xml
<ParticleEmitterComponent 
	_enabled="1"
	emitted_material_name="plasma_fading_bright"
	count_min="1"
	count_max="1"
	is_trail="1"
	trail_gap="1"
	lifetime_min="0.4"
	lifetime_max="0.4"
	emit_real_particles="0"
	render_on_grid="0"
	collide_with_grid="0"
	fade_based_on_lifetime="0"
	emit_cosmetic_particles="1"
	draw_as_long="0"
	emission_interval_min_frames="1"
	emission_interval_max_frames="1"
	is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: "plasma_fading_bright" - Emits bright, fading plasma particles.
*   **`is_trail`**: "1" - Creates a continuous trail.
*   **`trail_gap`**: "1" - Minimal gap between trail particles.
*   **`lifetime_min`/`max`**: "0.4" - Short lifetime for trail particles.

### Secondary Sprinkles

This emitter adds intermittent, cosmetic particle effects.

```xml
<ParticleEmitterComponent 
	_enabled="1"
	emitted_material_name="plasma_fading_bright"
	y_vel_min="-5"
	y_vel_max="5"
	count_min="1"
	count_max="1"
	is_trail="1"
	trail_gap="5"
	lifetime_min="0.2"
	lifetime_max="0.8"
	emit_real_particles="0"
	render_on_grid="1"
	emit_cosmetic_particles="1"
	fade_based_on_lifetime="0"
	emission_interval_min_frames="1"
	emission_interval_max_frames="2"
	is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: "plasma_fading_bright" - Emits bright, fading plasma particles.
*   **`y_vel_min`/`max`**: "-5" to "5" - Particles have a slight vertical velocity.
*   **`trail_gap`**: "5" - Larger gap between these intermittent particles.
*   **`lifetime_min`/`max`**: "0.2" to "0.8" - Variable lifetime for these particles.
*   **`emission_interval_min_frames`/`max_frames`**: "1" to "2" - Emits these particles every 1-2 frames.

## Variable Storage (`VariableStorageComponent`)

Stores variables associated with the entity.

```xml
<VariableStorageComponent
	name="projectile_file"
	value_string="data/entities/projectiles/megalaser_blue_beam.xml"
	>
</VariableStorageComponent>
```

*   **`name`**: "projectile_file" - Stores the path to this entity's XML file.
*   **`value_string`**: "data/entities/projectiles/megalaser_blue_beam.xml" - The actual file path.