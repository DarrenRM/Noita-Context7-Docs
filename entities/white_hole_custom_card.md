---
title: White Hole Custom Card
category: entities
---

# White Hole Custom Card

This document details the configuration for the "White Hole" custom card entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core of the White Hole card is defined by its `Entity` tag.

```xml
<Entity>
	<!-- ... entity components ... -->
</Entity>
```

## Base Configuration

The card inherits its fundamental properties from `base_custom_card.xml`.

### Sprite Component

Defines the visual representation of the card in the game's UI.

```xml
<SpriteComponent 
	image_file="data/ui_gfx/gun_actions/white_hole.png" 
	>
</SpriteComponent>
```

*   **`image_file`**: Specifies the texture used for the card's icon.

### Item Action Component

Assigns a unique identifier to the card's action.

```xml
<ItemActionComponent 
	_tags="enabled_in_world"
	action_id="WHITE_HOLE" >
</ItemActionComponent>
```

*   **`action_id`**: The internal ID for this action, crucial for game logic and scripting.

## Transform Component

Controls the positioning of the card when held by the player.

```xml
<InheritTransformComponent
	_tags="enabled_in_world,enabled_in_hand" >
  <Transform 
	position.x="8" 
	position.y="0" >
  </Transform>
</InheritTransformComponent>
```

*   **`position.x`**, **`position.y`**: Relative offset from the player's hand.

## Particle Emitter Component

Manages the cosmetic particle effects associated with the card.

```xml
<ParticleEmitterComponent 
	_tags="enabled_in_hand,item_identified"
	emitted_material_name="spark_white"
	offset.x="0"
	offset.y="0"
	x_pos_offset_min="-4"
	x_pos_offset_max="4"
	y_pos_offset_min="-4"
	y_pos_offset_max="4"
	x_vel_min="-8"
	x_vel_max="8"
	gravity.y="0.0"
	y_vel_min="-8"
	y_vel_max="8"
	count_min="1"
	count_max="2"
	lifetime_min="0.1"
	lifetime_max="0.6"
	create_real_particles="0"
	emit_cosmetic_particles="1"
	emission_interval_min_frames="5"
	emission_interval_max_frames="15"
	is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: The material used for the particles (e.g., "spark\_white").
*   **`x_pos_offset_min/max`**, **`y_pos_offset_min/max`**: Defines the area where particles are emitted.
*   **`x_vel_min/max`**, **`y_vel_min/max`**: Controls the initial velocity of the particles.
*   **`lifetime_min/max`**: Duration each particle exists.
*   **`emit_cosmetic_particles`**: Set to `1` to emit visual-only particles.
*   **`emission_interval_min/max_frames`**: Controls the frequency of particle emission.

## Light Component

Adds a light source when the card is identified and held.

```xml
<LightComponent 
	_tags="enabled_in_hand,item_identified"
	_enabled="1" 
	radius="30"
	fade_out_time="1.5" 
	r="80"
	g="80"
	b="80" >
</LightComponent>
```

*   **`radius`**: The range of the light effect.
*   **`fade_out_time`**: How long the light takes to fade.
*   **`r`**, **`g`**, **`b`**: RGB color values for the light.