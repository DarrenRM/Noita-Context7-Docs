---
title: Homing Orb Projectile
category: entities
---

# Homing Orb Projectile

This document details the configuration for a homing orb projectile entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core entity is a projectile with homing capabilities.

```xml
<Entity 
  name="$projectile_default" 
   >
```

## Base Projectile Properties

Inherits from `base_projectile.xml`, defining fundamental physics.

```xml
	<Base file="data/entities/base_projectile.xml" >
		<VelocityComponent
    		gravity_y="0"
			air_friction="-0.1"
			mass="0.05"
			>
    	</VelocityComponent> 
	</Base>
```

*   **`gravity_y="0"`**: The projectile is not affected by gravity.
*   **`air_friction="-0.1"`**: Applies a slight resistance to movement in the air.
*   **`mass="0.05"`**: Defines the projectile's mass.

## Homing Component

Enables the projectile to track and pursue targets.

```xml
	<HomingComponent
		target_tag="prey"
		homing_targeting_coeff="9"
		detect_distance="350"
		homing_velocity_multiplier="1.0"
		>
	</HomingComponent>
```

*   **`target_tag="prey"`**: The projectile will target entities with the "prey" tag.
*   **`homing_targeting_coeff="9"`**: Controls the strength of the homing behavior. Higher values mean more aggressive turning.
*   **`detect_distance="350"`**: The maximum distance at which the projectile can detect targets.
*   **`homing_velocity_multiplier="1.0"`**: Multiplies the projectile's current velocity when homing.

## Projectile Component

Defines the projectile's behavior, damage, and death effects.

```xml
  <ProjectileComponent 
    _enabled="1" 
	lob_min="0.8"
  	lob_max="1.0"
  	speed_min="100"
  	speed_max="120"
    die_on_low_velocity="0"
    on_death_explode="1"
    on_death_gfx_leave_sprite="0" 
    on_lifetime_out_explode="1"
	explosion_dont_damage_shooter="1"
    damage="0.3"
    on_collision_die="1"
    lifetime="150" >
    <config_explosion
      never_cache="1" 
      camera_shake="0.5" 
      explosion_radius="1" 
      explosion_sprite="data/particles/explosion_032_slimeburst_yellow.xml" 
      explosion_sprite_lifetime="0.0" 
      create_cell_probability="0" 
      create_cell_material="spark_blue" 
	  ray_energy="10000"
      hole_destroy_liquid="1" 
      hole_enabled="1" 
	  damage = "0.1"
      hole_image="data/temp/explosion_hole.png"
	  explosion_sprite_emissive="1"
	  explosion_sprite_additive="1"
      particle_effect="0" 
      damage_mortals="1"
	  physics_explosion_power.min="0"
      physics_explosion_power.max="0"
	  physics_throw_enabled="0"
      shake_vegetation="1"  
      sparks_enabled="1" 
	  spark_material="spark_yellow"
      sparks_count_max="16" 
      sparks_count_min="12"
      light_fade_time="1.2" 
	  light_r="180"
	  light_g="180"
      light_b="180"
      stains_enabled="1" 
      stains_image="data/temp/explosion_stain.png" >
    </config_explosion>
  </ProjectileComponent>
```

*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the projectile's arc.
*   **`speed_min="100"`, `speed_max="120"`**: Defines the projectile's initial speed range.
*   **`on_death_explode="1"`**: The projectile explodes upon death.
*   **`on_lifetime_out_explode="1"`**: The projectile explodes when its lifetime expires.
*   **`damage="0.3"`**: Base damage dealt by the projectile.
*   **`on_collision_die="1"`**: The projectile dies upon colliding with something.
*   **`lifetime="150"`**: The duration in frames before the projectile expires.
*   **`config_explosion`**:
    *   **`explosion_radius="1"`**: The radius of the explosion.
    *   **`explosion_sprite="..."`**: The visual effect of the explosion.
    *   **`damage="0.1"`**: Damage dealt by the explosion itself.
    *   **`hole_enabled="1"`**: Creates a hole in surfaces upon explosion.
    *   **`sparks_enabled="1"`**: Generates sparks upon explosion.
    *   **`light_r`, `light_g`, `light_b`**: Color of the light emitted by the explosion.

## Sprite Component

Defines the visual appearance of the projectile.

```xml
  <SpriteComponent 
    _enabled="1" 
    alpha="1" 
    image_file="data/projectiles_gfx/orb_yellow.xml" 
    rect_animation="fireball" 
	emissive="1"
    additive="1"
	offset_x="5" 
    offset_y="5" 
	update_transform_rotation="0"
	>
  </SpriteComponent>
```

*   **`image_file="data/projectiles_gfx/orb_yellow.xml"`**: Specifies the sprite sheet or animation file.
*   **`rect_animation="fireball"`**: Uses the "fireball" animation from the sprite sheet.
*   **`emissive="1"`, `additive="1"`**: Makes the sprite glow and blend additively.

## Sprite Particle Emitter Component

Adds small visual particles to the projectile.

```xml
	<SpriteParticleEmitterComponent
		sprite_file="data/particles/tinyspark_01.xml"
		emission_interval_min_frames="3"
		emission_interval_max_frames="4"
		count_min="1" count_max="2"
		randomize_rotation.min="-3.1415"
		randomize_rotation.max="3.1415"
		randomize_position.min_x="-8"
		randomize_position.max_x="8"
		randomize_position.min_y="-8"
		randomize_position.max_y="8"
		>
	</SpriteParticleEmitterComponent>
```

*   **`sprite_file="data/particles/tinyspark_01.xml"`**: The sprite used for the emitted particles.
*   **`emission_interval_...`**: Controls how often particles are emitted.
*   **`count_min`, `count_max`**: The number of particles emitted per interval.
*   **`randomize_rotation`, `randomize_position`**: Adds variation to particle orientation and placement.

## Light Component

Adds a light source to the projectile.

```xml
  <LightComponent 
    _enabled="1" 
    radius="150" 
    r="220"
    g="180"
    b="40">
  </LightComponent>
```

*   **`radius="150"`**: The radius of the light.
*   **`r`, `g`, `b`**: The color of the light (yellowish).

## Audio Components

Defines the sound effects associated with the projectile.

```xml
	<AudioComponent
		file="data/audio/Desktop/projectiles.bank"
		event_root="projectiles/magic" >
	</AudioComponent>
	
	<AudioLoopComponent
		file="data/audio/Desktop/projectiles.bank"
		event_name="projectiles/magic_orb/loop"
		auto_play="1">
	</AudioLoopComponent>
```

*   **`file`**: The audio bank file.
*   **`event_root`**: The general category of the sound.
*   **`event_name`**: Specific sound event for the loop.
*   **`auto_play="1"`**: The loop sound starts automatically.

## Hit Effect Component

Applies a special effect when the projectile hits an enemy.

```xml
	<HitEffectComponent 
        effect_hit="LOAD_UNIQUE_CHILD_ENTITY"
        value_string="data/entities/misc/gravity_field_enemy_short.xml" >
	</HitEffectComponent >
```

*   **`effect_hit="LOAD_UNIQUE_CHILD_ENTITY"`**: Loads another entity as a hit effect.
*   **`value_string="..."`**: Specifies the entity to load, in this case, a short-lived gravity field.

## Variable Storage Component

Stores a variable for potential use by other systems.

```xml
	<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/orb_homing.xml"
		>
	</VariableStorageComponent>
```

*   **`name="projectile_file"`**: The name of the variable.
*   **`value_string="..."`**: The value of the variable, pointing to this projectile's XML file.