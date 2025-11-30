---
title: Lifetime Custom Card
category: entities
---

# Lifetime Custom Card

This document describes the "Lifetime" custom card entity in Noita, focusing on its attributes relevant to AI-assisted modding.

## Entity Definition

The `Lifetime` card is a custom entity designed to be used as a spell card within the game.

```xml
<Entity>
	<Base file="data/entities/base_custom_card.xml" />
	<SpriteComponent image_file="data/ui_gfx/gun_actions/lifetime.png" />
	<ItemActionComponent action_id="LIFETIME" _tags="enabled_in_world" />
	<InheritTransformComponent parent_hotspot_tag="shoot_pos" _tags="enabled_in_world,enabled_in_hand" />
	<ParticleEmitterComponent
		emitted_material_name="spark_red"
		offset.x="0"
		offset.y="0"
		x_pos_offset_min="-3"
		x_pos_offset_max="3"
		y_pos_offset_min="1"
		y_pos_offset_max="-1"
		x_vel_min="-2"
		x_vel_max="2"
		y_vel_min="-20"
		y_vel_max="-10"
		count_min="1"
		count_max="1"
		lifetime_min="0.2"
		lifetime_max="0.3"
		create_real_particles="0"
		emit_cosmetic_particles="1"
		emission_interval_min_frames="10"
		emission_interval_max_frames="25"
		is_emitting="1"
		_tags="enabled_in_hand,item_identified" />
</Entity>
```

## Key Components and Attributes

### Base Entity

*   **`<Base file="data/entities/base_custom_card.xml" />`**: Inherits core functionality and properties from the generic custom card entity.

### Sprite Component

*   **`<SpriteComponent image_file="data/ui_gfx/gun_actions/lifetime.png" />`**: Defines the visual representation of the card in the game's UI.

### Item Action Component

*   **`<ItemActionComponent action_id="LIFETIME" _tags="enabled_in_world" />`**: Assigns a unique identifier (`LIFETIME`) to this card's action and specifies that it can be enabled in the game world.

### Inheritance Transform Component

*   **`<InheritTransformComponent parent_hotspot_tag="shoot_pos" _tags="enabled_in_world,enabled_in_hand" />`**: Controls how the card's transform (position, rotation) is inherited, specifically linking it to the `shoot_pos` hotspot when held in hand or in the world.

### Particle Emitter Component

This component governs the cosmetic particle effects associated with the card when it's held or identified.

*   **`emitted_material_name="spark_red"`**: The type of material used for the emitted particles.
*   **`offset.x`, `offset.y`**: The base position offset for particle emission.
*   **`x_pos_offset_min`, `x_pos_offset_max`**: Defines the horizontal spread of particle emission.
*   **`y_pos_offset_min`, `y_pos_offset_max`**: Defines the vertical spread of particle emission.
*   **`x_vel_min`, `x_vel_max`**: The minimum and maximum horizontal velocity of emitted particles.
*   **`y_vel_min`, `y_vel_max`**: The minimum and maximum vertical velocity of emitted particles.
*   **`count_min`, `count_max`**: The range for the number of particles emitted per burst.
*   **`lifetime_min`, `lifetime_max`**: The duration (in seconds) each particle exists.
*   **`create_real_particles="0"`**: Indicates that these are cosmetic particles, not physical entities.
*   **`emit_cosmetic_particles="1"`**: Explicitly enables cosmetic particle emission.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: The range of frames between particle emission bursts.
*   **`is_emitting="1"`**: Ensures the particle emitter is active.
*   **`_tags="enabled_in_hand,item_identified"`**: Specifies when the particle emitter is active (when the item is in hand and identified).