---
title: Spore Pod Spike Projectile
category: entities
---

# Spore Pod Spike Projectile

This document details the configuration for the "spore_pod_spike" projectile entity in Noita, useful for AI-assisted modding.

## Core Entity Configuration

The `Entity` tag defines the fundamental properties of the projectile.

```xml
<Entity 
	name="$projectile_default" 
	>
```

## Base Projectile Properties

The `Base` tag inherits properties from the generic projectile.

### Velocity Component

Controls the projectile's movement physics.

```xml
<Base file="data/entities/base_projectile.xml" >
	<VelocityComponent
		gravity_y="250"       // Downward acceleration due to gravity.
		air_friction="1.3"    // Resistance to movement in the air.
		mass="0.07"           // The projectile's mass, affecting how it interacts with forces.
		>
	</VelocityComponent>
</Base>
```

## Projectile Component

This is the primary component defining the projectile's behavior and interactions.

### Key Attributes:

```xml
<ProjectileComponent 
	lob_min="0.5"             // Minimum lobbing angle (in radians).
	lob_max="0.7"             // Maximum lobbing angle (in radians).
	friction="1"              // Friction applied to the projectile.
	direction_random_rad="3.14151" // Maximum random deviation in projectile direction (in radians).
	on_death_explode="0"      // Whether the projectile explodes upon death.
	on_death_gfx_leave_sprite="1" // Whether to leave a sprite graphic when it dies.
	on_lifetime_out_explode="0" // Whether the projectile explodes when its lifetime expires.
	explosion_dont_damage_shooter="1" // Prevents the explosion from damaging the entity that fired it.
	on_collision_die="1"      // Whether the projectile dies upon collision.
	on_lifetime_out_die="1"   // Whether the projectile dies when its lifetime expires.
	lifetime="750"            // The base duration of the projectile in frames.
	damage="0.1"              // The base damage dealt by the projectile.
	damage_scaled_by_speed="0" // Whether damage is increased based on projectile speed.
	lifetime_randomness="7"   // Adds random variation to the projectile's lifetime.
	ragdoll_force_multiplier="0" // Multiplier for ragdoll force applied on impact.
	hit_particle_force_multiplier="0.1" // Multiplier for particle force on hit.
	create_shell_casing="0"   // Whether to create a shell casing effect.
	muzzle_flash_file=""      // Path to a muzzle flash effect file.
	shoot_light_flash_radius="0" // Radius of light flash when shot.
	die_on_low_velocity="0"   // Whether the projectile dies if its velocity drops too low.
	die_on_low_velocity_limit="5" // The velocity limit for dying on low velocity.
	collide_with_shooter_frames="6" // Number of frames the projectile will ignore collisions with its shooter.
	friendly_fire="1"         // Whether the projectile can damage friendly entities.
	velocity_sets_scale="0"   // Whether the projectile's velocity affects its scale.
	knockback_force="1.0"     // The force of knockback applied on impact.
	bounces_left="1"          // The number of bounces the projectile can perform.
	>
	<config_explosion>
	</config_explosion>
</ProjectileComponent>
```

## Initial Velocity Configuration

This component sets the projectile's starting speed and direction.

### Key Attributes:

```xml
<SetStartVelocityComponent
	randomize_speed.min="150"     // Minimum initial speed.
	randomize_speed.max="200"     // Maximum initial speed.
	randomize_angle.min="0"       // Minimum initial angle deviation (in radians).
	randomize_angle.max="6.283185" // Maximum initial angle deviation (in radians).
	>
</SetStartVelocityComponent>
```

## Visual Representation

The `SpriteComponent` defines the visual appearance of the projectile.

### Key Attributes:

```xml
<SpriteComponent 
	image_file="data/projectiles_gfx/spore_pod_spike.xml" > // Path to the sprite's XML definition.
</SpriteComponent>
```

## Particle Effects

The `ParticleEmitterComponent` defines any particle effects associated with the projectile.

### Key Attributes:

```xml
<ParticleEmitterComponent 
	emitted_material_name="smoke" // The material of the particles to emit.
	offset.x="0"                  // X-axis offset for particle emission.
	offset.y="0"                  // Y-axis offset for particle emission.
	x_pos_offset_min="-1"         // Minimum X-position offset for emitted particles.
	y_pos_offset_min="-1"         // Minimum Y-position offset for emitted particles.
	x_pos_offset_max="1"          // Maximum X-position offset for emitted particles.
	y_pos_offset_max="1"          // Maximum Y-position offset for emitted particles.
	x_vel_min="-10"               // Minimum X-velocity for emitted particles.
	x_vel_max="10"                // Maximum X-velocity for emitted particles.
	y_vel_min="-10"               // Minimum Y-velocity for emitted particles.
	y_vel_max="10"                // Maximum Y-velocity for emitted particles.
	count_min="0"                 // Minimum number of particles to emit per interval.
	count_max="1"                 // Maximum number of particles to emit per interval.
	lifetime_min="0.1"            // Minimum lifetime of emitted particles.
	lifetime_max="0.3"            // Maximum lifetime of emitted particles.
	create_real_particles="1"    // Whether to create actual game particles.
	emit_cosmetic_particles="0"   // Whether to emit cosmetic-only particles.
	emission_interval_min_frames="1" // Minimum frames between particle emissions.
	emission_interval_max_frames="1" // Maximum frames between particle emissions.
	is_emitting="1"               // Whether the emitter is currently active.
	>
</ParticleEmitterComponent>
```