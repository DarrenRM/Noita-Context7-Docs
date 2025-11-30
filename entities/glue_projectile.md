---
title: Glue Projectile
category: entities
---

# Glue Projectile

This document details the configuration for the Glue projectile entity in Noita, focusing on its behavior and visual representation for AI-assisted modding.

## Core Entity Configuration

The main `Entity` tag defines the fundamental properties of the glue projectile.

```xml
<Entity tags="glue">
	<!-- ... components ... -->
</Entity>
```

### Key Attributes:

*   **`tags="glue"`**: Identifies this entity as a glue projectile.

## Components

### VelocityComponent

Controls the projectile's movement and interaction with gravity.

```xml
<VelocityComponent
	gravity_y="0"
	terminal_velocity="10"
	>
</VelocityComponent>
```

*   **`gravity_y="0"`**: The glue projectile is not affected by gravity.
*   **`terminal_velocity="10"`**: Sets a maximum speed for the projectile.

### SpriteComponent

Defines the visual appearance of the glue.

```xml
<SpriteComponent
	alpha="0.6"
	image_file="data/projectiles_gfx/glue.xml"
	>
</SpriteComponent>
```

*   **`alpha="0.6"`**: The transparency level of the glue sprite.
*   **`image_file="data/projectiles_gfx/glue.xml"`**: Specifies the graphical asset used for the glue.

### Glue Anchors

These entities are responsible for the "sticking" behavior.

```xml
<Entity tags="glue_anchor">
	<Base file="data/entities/projectiles/glue_anchor.xml" />
</Entity>
<Entity tags="glue_anchor">
	<Base file="data/entities/projectiles/glue_anchor.xml" />
</Entity>
```

*   **`tags="glue_anchor"`**: Identifies these as components that attach to surfaces.
*   **`<Base file="..." />`**: Inherits properties from a predefined `glue_anchor.xml` entity.

### LuaComponent (Scripting)

These components leverage Lua scripts to manage the glue's dynamic behavior.

#### `glue_stretch.lua`

Manages the stretching and breaking of the glue between anchors.

```xml
<LuaComponent
	script_source_file="data/scripts/projectiles/glue_stretch.lua"
	execute_every_n_frame="1"
	>
</LuaComponent>
```

*   **`script_source_file="..."`**: The path to the Lua script.
*   **`execute_every_n_frame="1"`**: The script runs every frame, allowing for real-time updates.

#### `glue_init.lua`

Initializes the glue projectile and finds targets for its anchors.

```xml
<LuaComponent
	script_source_file="data/scripts/projectiles/glue_init.lua"
	execute_on_added="1"
	remove_after_executed="1"
	>
</LuaComponent>
```

*   **`script_source_file="..."`**: The path to the Lua script.
*   **`execute_on_added="1"`**: The script runs once when the entity is added to the game.
*   **`remove_after_executed="1"`**: The script component is removed after its initial execution.

### LifetimeComponent

Determines how long the glue projectile persists.

```xml
<LifetimeComponent
	lifetime="500"
	>
</LifetimeComponent>
```

*   **`lifetime="500"`**: The glue will exist for 500 frames.

### AudioComponent

Manages the sound effects associated with the glue projectile.

```xml
<AudioComponent
	file="data/audio/Desktop/projectiles.bank"
	event_root="projectiles/slime">
</AudioComponent>
```

*   **`file="..."`**: Specifies the audio bank file.
*   **`event_root="..."`**: Defines the root event for projectile sounds, specifically for "slime" type sounds.

### ParticleEmitterComponent (Commented Out)

This section, currently commented out, defines a particle emitter that could be used to generate cosmetic particles.

```xml
<!--
<ParticleEmitterComponent
	emitted_material_name="glue"
	emitter_lifetime_frames="3"
	offset.x="0"
	offset.y="0"
	x_pos_offset_min="-2"
	x_pos_offset_max="2"
	y_pos_offset_min="-2"
	y_pos_offset_max="2"
	x_vel_min="-40"
	x_vel_max="40"
	y_vel_min="-40"
	y_vel_max="-10"
	count_min="4"
	count_max="6"
	lifetime_min="0.2"
	lifetime_max="0.3"
	create_real_particles="1"
	emit_cosmetic_particles="1"
	emission_interval_min_frames="1"
	emission_interval_max_frames="1"
	is_emitting="1" >
</ParticleEmitterComponent>
-->
```

*   **`emitted_material_name="glue"`**: The material of the particles to be emitted.
*   **`count_min`/`count_max`**: The range for the number of particles emitted per burst.
*   **`lifetime_min`/`lifetime_max`**: The duration of each particle.
*   **`is_emitting="1"`**: Enables the particle emission.