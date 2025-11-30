---
title: Pink Big Super Shrapnel Orb Projectile
category: entities
---

# Pink Big Super Shrapnel Orb Projectile

This document details the configuration for a specific projectile entity in Noita, designed to function as a "Pink Big Super Shrapnel Orb". It outlines its physical properties, projectile behavior, visual representation, and particle effects.

## Entity Definition

The core entity definition for this projectile.

```xml
<Entity 
	name="$projectile_default"
	tags="resist_repulsion"
	>
```

*   **`name`**: `$projectile_default` - Indicates this entity inherits default projectile properties.
*   **`tags`**: `resist_repulsion` - Applies a tag that may influence interactions with other game elements.

## Base Projectile Properties

Inherits and modifies fundamental projectile physics.

```xml
<Base file="data/entities/base_projectile.xml" >
	<VelocityComponent
		gravity_y="0"
		air_friction="1.2"
		terminal_velocity="600"
		mass="0.8"
		>
	</VelocityComponent> 
</Base>
```

*   **`gravity_y`**: `0` - The projectile is not affected by gravity.
*   **`air_friction`**: `1.2` - A moderate amount of air resistance.
*   **`terminal_velocity`**: `600` - The maximum speed the projectile can reach due to air friction.
*   **`mass`**: `0.8` - The projectile's mass, influencing its momentum.

## Projectile Component

Defines the specific behavior and effects of this projectile.

```xml
<ProjectileComponent 
	lob_min="0.8"
	lob_max="1.0"
	speed_min="50"
	speed_max="50"
	direction_random_rad="3.14151"
	die_on_low_velocity="0"
	on_death_explode="1"
	on_death_gfx_leave_sprite="0" 
	on_lifetime_out_explode="1"
	explosion_dont_damage_shooter="1"
	damage="0.7"
	on_collision_die="1"
	bounces_left="1"
	bounce_at_any_angle="1"
	bounce_energy="0.8"
	lifetime="100"
	lifetime_randomness="40"
	knockback_force="0.1"
	>
	<!-- ... config_explosion ... -->
</ProjectileComponent>
```

### Key Projectile Attributes:

*   **`lob_min` / `lob_max`**: `0.8` / `1.0` - Controls the arc or lob of the projectile.
*   **`speed_min` / `speed_max`**: `50` / `50` - The projectile travels at a fixed speed of 50.
*   **`direction_random_rad`**: `3.14151` - Introduces significant randomness in the projectile's initial direction (nearly a full circle).
*   **`die_on_low_velocity`**: `0` - The projectile does not die simply by slowing down.
*   **`on_death_explode`**: `1` - The projectile explodes upon death.
*   **`on_lifetime_out_explode`**: `1` - The projectile explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter`**: `1` - The explosion will not harm the entity that fired it.
*   **`damage`**: `0.7` - The base damage dealt by the projectile itself.
*   **`on_collision_die`**: `1` - The projectile dies upon colliding with something.
*   **`bounces_left`**: `1` - The projectile can bounce once.
*   **`bounce_at_any_angle`**: `1` - The projectile can bounce regardless of the collision angle.
*   **`bounce_energy`**: `0.8` - The projectile retains 80% of its energy after a bounce.
*   **`lifetime`**: `100` - The base duration of the projectile's existence.
*   **`lifetime_randomness`**: `40` - Adds variability to the projectile's lifetime.
*   **`knockback_force`**: `0.1` - A small amount of knockback is applied.

### Explosion Configuration (`config_explosion`):

Defines the properties of the explosion that occurs upon the projectile's death.

```xml
		<config_explosion
			never_cache="1" 
			camera_shake="0.0" 
			explosion_radius="6" 
			explosion_sprite="data/particles/explosion_008_pink.xml" 
			explosion_sprite_lifetime="0.0" 
			create_cell_probability="1" 
			create_cell_material="plasma_fading_pink" 
			ray_energy="10000"
			hole_destroy_liquid="1" 
			hole_enabled="1" 
			damage="0"
			hole_image="data/temp/explosion_hole.png"
			explosion_sprite_emissive="0"
			explosion_sprite_additive="1"
			particle_effect="0" 
			damage_mortals="1"
			physics_explosion_power.min="0.4" 
			physics_explosion_power.max="0.6"
			physics_throw_enabled="1"
			shake_vegetation="1"  
			sparks_enabled="1" 
			sparks_count_max="8" 
			sparks_count_min="4"
			spark_material="plasma_fading_pink"
			light_fade_time="1.2" 
			light_r="155"
			light_g="15"
			light_b="140"
			stains_enabled="1" 
			stains_image="data/temp/explosion_stain.png"
			audio_enabled="0" >
		</config_explosion>
```

*   **`explosion_radius`**: `6` - The area of effect for the explosion.
*   **`explosion_sprite`**: `data/particles/explosion_008_pink.xml` - The visual effect used for the explosion.
*   **`create_cell_probability`**: `1` - Guarantees the creation of cells upon explosion.
*   **`create_cell_material`**: `plasma_fading_pink` - The material of the cells created.
*   **`ray_energy`**: `10000` - High energy for potential ray interactions.
*   **`hole_destroy_liquid`**: `1` - The explosion can destroy liquids.
*   **`hole_enabled`**: `1` - The explosion leaves a hole in surfaces.
*   **`damage`**: `0` - The explosion itself does not deal direct damage (damage is from projectile component).
*   **`damage_mortals`**: `1` - The explosion can damage living entities.
*   **`physics_explosion_power.min` / `max`**: `0.4` / `0.6` - The force applied to physics objects.
*   **`sparks_enabled`**: `1` - Sparks are generated by the explosion.
*   **`spark_material`**: `plasma_fading_pink` - The material of the sparks.
*   **`light_r` / `g` / `b`**: `155` / `15` / `140` - Defines the color of the light emitted by the explosion.
*   **`stains_enabled`**: `1` - The explosion leaves stains on surfaces.

## Initial Velocity Component

Determines how the projectile is launched.

```xml
<SetStartVelocityComponent
	randomize_speed.min="200"
	randomize_speed.max="400"
	randomize_angle.min="0"
	randomize_angle.max="3.1"
	>
</SetStartVelocityComponent>
```

*   **`randomize_speed.min` / `max`**: `200` / `400` - The projectile's initial speed will be randomized within this range.
*   **`randomize_angle.min` / `max`**: `0` / `3.1` - The projectile's initial direction will be randomized within a wide angle (close to 180 degrees).

## Sprite Component

Defines the visual appearance of the projectile.

```xml
<SpriteComponent 
	_enabled="1" 
	alpha="1" 
	image_file="data/projectiles_gfx/orb_tiny.xml" 
	emissive="0"
	additive="1"
	update_transform_rotation="0"
	>
</SpriteComponent>
```

*   **`image_file`**: `data/projectiles_gfx/orb_tiny.xml` - Specifies the graphical asset used for the projectile.
*   **`additive`**: `1` - The sprite uses additive blending, making it appear brighter.

## Particle Emitters

Defines visual effects associated with the projectile.

### Trail Emitter:

```xml
	<!-- trail -->
	<ParticleEmitterComponent 
		emitted_material_name="plasma_fading_pink"
		offset.x="0"
		offset.y="0"
		gravity.y="19.0"
		x_vel_min="0"
		x_vel_max="0"
		y_vel_min="0"
		y_vel_max="0"
		friction="0"
		count_min="1"
		count_max="1"
		lifetime_min="0.05"
		lifetime_max="1.15"
		emit_real_particles="0"
		render_on_grid="1"
		is_trail="0"
		trail_gap="3"
		emit_cosmetic_particles="1"
		fade_based_on_lifetime="1"
		emission_interval_min_frames="2"
		emission_interval_max_frames="2"
		is_emitting="1" >
	</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: `plasma_fading_pink` - The material of the particles emitted.
*   **`gravity.y`**: `19.0` - Particles are affected by gravity.
*   **`lifetime_min` / `max`**: `0.05` / `1.15` - The duration particles exist.
*   **`is_trail`**: `0` - This emitter is not configured as a continuous trail.
*   **`emit_cosmetic_particles`**: `1` - Emits particles for visual flair.

### Poof Emitter (On Death):

```xml
	<!-- poof -->
	<ParticleEmitterComponent 
		emitted_material_name="plasma_fading_pink"
		emitter_lifetime_frames="2"
		offset.x="0"
		offset.y="0"
		gravity.y="0.0"
		area_circle_radius.min="3"
		area_circle_radius.max="3"
		velocity_always_away_from_center="40"
		friction="1.5"
		count_min="10"
		count_max="10"
		lifetime_min="0.5"
		lifetime_max="2.0"
		emit_real_particles="0"
		render_on_grid="1"
		emit_cosmetic_particles="1"
		emission_interval_min_frames="1"
		emission_interval_max_frames="1"
		is_emitting="1" >
	</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: `plasma_fading_pink` - The material of the particles emitted.
*   **`emitter_lifetime_frames`**: `2` - The emitter is active for a very short duration.
*   **`gravity.y`**: `0.0` - Particles are not affected by gravity.
*   **`area_circle_radius.min` / `max`**: `3` / `3` - Particles are emitted from a small circular area.
*   **`velocity_always_away_from_center`**: `40` - Particles are propelled outwards from the emission point.
*   **`lifetime_min` / `max`**: `0.5` / `2.0` - The duration particles exist.
*   **`emit_cosmetic_particles`**: `1` - Emits particles for visual flair.

## Variable Storage

Stores custom variables for use within the game.

```xml
	<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/orb_pink_super_shrapnel.xml"
		>
	</VariableStorageComponent>
```

*   **`name`**: `projectile_file` - A variable named "projectile\_file".
*   **`value_string`**: `data/entities/projectiles/orb_pink_super_shrapnel.xml` - Stores the path to another projectile XML file, likely indicating this entity is a precursor or variant.