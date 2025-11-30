---
title: Polymorph Field Projectile
category: entities
---

# Polymorph Field Projectile

This document details the configuration for the "Polymorph Field" projectile entity in Noita, primarily focusing on its visual and functional aspects for AI-assisted modding.

## Core Entity Configuration

The projectile is defined as an `Entity` with a base file inherited from `data/entities/projectiles/deck/base_field.xml`.

```xml
<Entity 
  name="$projectile_default" 
   >
  <GameAreaEffectComponent
      radius="28"
    >
  </GameAreaEffectComponent>
  
  <Base file="data/entities/projectiles/deck/base_field.xml">
    <!-- ... other components ... -->
  </Base>
</Entity>
```

### Key Attributes:

*   **`name`**: `$projectile_default` - Indicates this entity uses a default projectile naming convention.
*   **`GameAreaEffectComponent`**:
    *   **`radius`**: `28` - Defines the area of effect radius for this projectile.

## Particle Emitters

The projectile utilizes two `ParticleEmitterComponent` instances to generate visual effects.

### Emitter 1 (Primary Glow)

```xml
	<ParticleEmitterComponent 
		emitted_material_name="plasma_fading_pink"
		gravity.y="0.0"
		lifetime_min="0.2"
		lifetime_max="0.8"
		count_min="2"
		count_max="4"
		render_on_grid="1"
		fade_based_on_lifetime="1"
		area_circle_radius.max="28"
		cosmetic_force_create="0"
		airflow_force="0.5"
		airflow_time="0.01"
		airflow_scale="0.05"
		emission_interval_min_frames="1"
		emission_interval_max_frames="1"
		emit_cosmetic_particles="1"
		is_emitting="1" >
	</ParticleEmitterComponent>
```

#### Key Attributes:

*   **`emitted_material_name`**: `plasma_fading_pink` - Specifies the material used for the emitted particles.
*   **`lifetime_min` / `lifetime_max`**: `0.2` / `0.8` - Controls the duration of individual particles.
*   **`count_min` / `count_max`**: `2` / `4` - Determines the number of particles emitted per interval.
*   **`area_circle_radius.max`**: `28` - Sets the maximum radius for particle emission.
*   **`airflow_force`**: `0.5` - Influences particle movement due to airflow.

### Emitter 2 (Outer Ring)

```xml
	<ParticleEmitterComponent 
		emitted_material_name="plasma_fading_pink"
		gravity.y="0.0"
		lifetime_min="0.5"
		lifetime_max="1.5"
		count_min="4"
		count_max="4"
		render_on_grid="1"
		fade_based_on_lifetime="1"
		area_circle_radius.min="28"
		area_circle_radius.max="28"
		cosmetic_force_create="0"
		airflow_force="0.3"
		airflow_time="0.01"
		airflow_scale="0.05"
		emission_interval_min_frames="1"
		emission_interval_max_frames="1"
		emit_cosmetic_particles="1"
		is_emitting="1" >
	</ParticleEmitterComponent>
```

#### Key Attributes:

*   **`emitted_material_name`**: `plasma_fading_pink` - Same material as Emitter 1.
*   **`lifetime_min` / `lifetime_max`**: `0.5` / `1.5` - Longer lifetime for these particles.
*   **`count_min` / `count_max`**: `4` / `4` - Emits a consistent number of particles.
*   **`area_circle_radius.min` / `area_circle_radius.max`**: `28` / `28` - Particles are emitted specifically at the edge of the effect radius.
*   **`airflow_force`**: `0.3` - Slightly less airflow influence than Emitter 1.

## Sprite and Visual Components

### Main Sprite

```xml
		<SpriteComponent 
			image_file="data/projectiles_gfx/blast_polymorph.xml"
			>
		</SpriteComponent>
```

*   **`image_file`**: `data/projectiles_gfx/blast_polymorph.xml` - Specifies the graphical asset for the projectile's main visual.

### Shine Particles

```xml
		<SpriteParticleEmitterComponent
			sprite_file="data/particles/shine_03.xml"
			lifetime="2"
			color.r="1" color.g="1" color.b="1" color.a="1"
			color_change.r="0" color_change.g="0" color_change.b="0" color_change.a="-1"
			randomize_rotation.min="-3.1415"
			randomize_rotation.max="3.1415"
			randomize_angular_velocity.min="-15"
			randomize_angular_velocity.max="15"
			is_emitting="1"
			>
		</SpriteParticleEmitterComponent>
```

*   **`sprite_file`**: `data/particles/shine_03.xml` - Uses a shine particle effect.
*   **`lifetime`**: `2` - Duration of the shine effect.
*   **`color`**: White (`1, 1, 1, 1`) - Initial color of the shine.
*   **`color_change.a`**: `-1` - The alpha (transparency) of the shine decreases over its lifetime.
*   **`randomize_rotation` / `randomize_angular_velocity`**: These attributes control the random spinning and rotation speed of the shine particles.

## Projectile Functionality

### Projectile Component

```xml
		<ProjectileComponent 
			damage_game_effect_entities="data/entities/misc/effect_polymorph.xml,"
			friendly_fire="0"
			>
			<config_explosion
				explosion_sprite="data/particles/blast_out_polymorph.xml"
				>
			</config_explosion>
		</ProjectileComponent>
```

*   **`damage_game_effect_entities`**: `data/entities/misc/effect_polymorph.xml` - Links to the entity that defines the polymorph effect applied on hit.
*   **`friendly_fire`**: `0` - This projectile does not affect friendly entities.
*   **`config_explosion.explosion_sprite`**: `data/particles/blast_out_polymorph.xml` - Specifies the visual effect for when the projectile explodes.

## Audio Component

```xml
		<AudioLoopComponent
		  file="data/audio/Desktop/projectiles.bank"
		  event_name="player_projectiles/field_transmutation/loop"
		  auto_play="1" >
	  </AudioLoopComponent>
```

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound event.
*   **`event_name`**: `player_projectiles/field_transmutation/loop` - The specific sound event triggered by this projectile.
*   **`auto_play`**: `1` - The sound effect plays automatically when the projectile is active.