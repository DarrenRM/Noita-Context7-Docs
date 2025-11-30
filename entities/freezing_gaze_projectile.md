---
title: Freezing Gaze Projectile
category: entities
---

# Freezing Gaze Projectile

This document details the configuration for the "Freezing Gaze" projectile in Noita, designed for AI-assisted modding.

## Entity Definition

The core entity defines a player projectile with specific behaviors and properties.

```xml
<Entity 
	name="$projectile_default" tags="projectile_player"
	>
```

## Base Projectile Configuration

Inherits fundamental projectile properties, with a specific modification to gravity.

```xml
	<Base file="data/entities/base_projectile.xml" >
		<VelocityComponent
			gravity_y="0"
			>
		</VelocityComponent> 
	</Base>
```

### Key Attributes:

*   **`gravity_y="0"`**: This projectile is not affected by gravity, allowing for straight-line travel.

## Projectile Component

This component governs the projectile's physical behavior, damage, and lifespan.

```xml
	<ProjectileComponent 
		_enabled="1" 
		lob_min="0.8"
		lob_max="1.0"
		speed_min="40"
		speed_max="40"
		die_on_low_velocity="0"
		on_death_explode="0"
		on_death_gfx_leave_sprite="0" 
		on_lifetime_out_explode="0"
		on_collision_die="1"
		shoot_light_flash_radius="15"
		shoot_light_flash_r="250"
		shoot_light_flash_g="80"
		shoot_light_flash_b="255"
		damage="0.0"
		lifetime="44" 
		penetrate_entities="1"
		>
	</ProjectileComponent>
```

### Key Attributes:

*   **`lob_min`, `lob_max`**: Controls the projectile's arc. Values close to 1.0 suggest a very straight trajectory.
*   **`speed_min`, `speed_max`**: Sets the projectile's speed to a constant 40.
*   **`die_on_low_velocity`, `on_death_explode`, `on_lifetime_out_explode`**: All set to `0`, meaning the projectile does not explode or die due to low velocity or when its lifetime expires.
*   **`on_collision_die="1"`**: The projectile will be destroyed upon colliding with an entity.
*   **`shoot_light_flash_radius`, `shoot_light_flash_r`, `shoot_light_flash_g`, `shoot_light_flash_b`**: Defines a light flash effect upon shooting, with a radius of 15 and a distinct purple hue.
*   **`damage="0.0"`**: This projectile deals no direct damage. Its effect is likely handled by the Lua script.
*   **`lifetime="44"`**: The projectile exists for 44 frames.
*   **`penetrate_entities="1"`**: The projectile can pass through multiple entities.

## Lua Component

This component links the projectile to a custom Lua script for advanced behavior.

```xml
	<LuaComponent
		script_source_file="data/scripts/projectiles/freezing_gaze.lua"
		execute_every_n_frame="1"
		>
	</LuaComponent>
```

### Key Attributes:

*   **`script_source_file`**: Specifies the path to the custom Lua script (`data/scripts/projectiles/freezing_gaze.lua`) responsible for the projectile's unique effects, such as freezing.
*   **`execute_every_n_frame="1"`**: The associated Lua script will execute every frame, allowing for continuous effect application or checks.

## Audio Component

Defines the sound effects associated with this projectile.

```xml
	<AudioComponent
		file="data/audio/Desktop/projectiles.bank"
		event_root="player_projectiles/freezing_gaze">
	</AudioComponent>
```

### Key Attributes:

*   **`file`**: Points to the audio bank containing the sound effects.
*   **`event_root`**: Specifies the specific sound event to trigger for this projectile, named `player_projectiles/freezing_gaze`.