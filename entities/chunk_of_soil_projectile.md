---
title: Chunk of Soil Projectile
category: entities
---

# Chunk of Soil Projectile

This document details the configuration of the "Chunk of Soil" projectile entity in Noita, focusing on its behavior and effects when used in modding.

## Entity Definition

The core of this projectile is defined by the `<Entity>` tag, which inherits base projectile properties from `data/entities/base_projectile.xml`.

```xml
<Entity name="$projectile_default" >
	<Base file="data/entities/base_projectile.xml" >
		<VelocityComponent
			gravity_y="100">
		</VelocityComponent>
	</Base>
    <!-- ... other components ... -->
</Entity>
```

### Key Attributes:

*   **`gravity_y="100"`**: This attribute within `<VelocityComponent>` dictates the projectile's downward acceleration due to gravity. A value of `100` provides a moderate gravitational pull.

## Projectile Component

The `<ProjectileComponent>` defines the specific behaviors and characteristics of the projectile.

```xml
	<ProjectileComponent
		_enabled="1"
		lob_min="0.8"
		lob_max="1.0"
		speed_min="0"
		speed_max="10"
		on_death_explode="1"
		on_death_gfx_leave_sprite="0"
		on_lifetime_out_explode="1"
		explosion_dont_damage_shooter="0"
		die_on_low_velocity="1"
		damage="0"
		on_collision_die="1"
		lifetime="1" >
        <!-- ... config_explosion ... -->
	</ProjectileComponent>
```

### Key Attributes:

*   **`_enabled="1"`**: Enables this component.
*   **`lob_min="0.8"`, `lob_max="1.0"`**: These control the "lobbing" behavior, influencing the arc of the projectile. Values closer to 1.0 suggest a more direct trajectory.
*   **`speed_min="0"`, `speed_max="10"`**: Defines the range of initial speeds for the projectile.
*   **`on_death_explode="1"`**: When the projectile dies (e.g., due to lifetime or collision), it will trigger an explosion.
*   **`on_lifetime_out_explode="1"`**: The projectile will explode when its `lifetime` expires.
*   **`die_on_low_velocity="1"`**: The projectile will be destroyed if its velocity drops below a certain threshold.
*   **`damage="0"`**: This projectile does not inflict direct damage.
*   **`on_collision_die="1"`**: The projectile will be destroyed upon colliding with an object.
*   **`lifetime="1"`**: The projectile exists for a maximum of 1 second before expiring.

### `config_explosion`

This nested element within `<ProjectileComponent>` configures the explosion that occurs when the projectile dies.

```xml
	<config_explosion
		never_cache="0"
		camera_shake="0"
		explosion_radius="15"
		explosion_sprite=""
		damage="0"
		explosion_sprite_lifetime="0"
		create_cell_probability="100"
		create_cell_material="soil"
		hole_destroy_liquid="0"
		hole_enabled="1"
		particle_effect="0"
		physics_explosion_power.min="0"
		physics_explosion_power.max="0"
		physics_throw_enabled="0"
		shake_vegetation="0"
		sparks_enabled="0"
		stains_enabled="0"
		ray_energy="0">
	</config_explosion>
```

#### Key Attributes:

*   **`explosion_radius="15"`**: The radius of the explosion effect.
*   **`create_cell_probability="100"`**: There is a 100% chance that the explosion will create new cells.
*   **`create_cell_material="soil"`**: The material of the cells created by the explosion is "soil". This is the primary effect of this projectile.
*   **`hole_enabled="1"`**: The explosion will create a hole in the environment.
*   **`damage="0"`**: The explosion itself does not deal damage.
*   **`physics_explosion_power.min="0"`, `physics_explosion_power.max="0"`**: The explosion does not apply any physics force to nearby objects.

## Audio Component

This component defines the sound played when the projectile is active.

```xml
  <AudioComponent
      file="data/audio/Desktop/projectiles.bank"
      event_root="player_projectiles/summon_generic">
  </AudioComponent>
```

### Key Attributes:

*   **`file="data/audio/Desktop/projectiles.bank"`**: Specifies the audio bank containing the sound effects.
*   **`event_root="player_projectiles/summon_generic"`**: The specific sound event to trigger, indicating a generic player projectile summon sound.

## Variable Storage Component

This component stores a reference to the projectile's own XML file.

```xml
  <VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/chunk_of_soil.xml"
		>
	</VariableStorageComponent>
```

### Key Attributes:

*   **`name="projectile_file"`**: The name of the variable.
*   **`value_string="data/entities/projectiles/chunk_of_soil.xml"`**: The value of the variable, pointing to the projectile's definition file. This is useful for other entities or scripts that might need to reference this specific projectile.