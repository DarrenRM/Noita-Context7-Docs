---
title: Decelerating Shot Custom Card
category: entities
---

# Decelerating Shot Custom Card

This document details the configuration for the "Decelerating Shot" custom card in Noita, intended for AI-assisted modding.

## Entity Configuration

The core of this custom card is defined within an `<Entity>` tag, inheriting from a base custom card.

```xml
<Entity>
	<Base file="data/entities/base_custom_card.xml" >
		<SpriteComponent
			image_file="data/ui_gfx/gun_actions/decelerating_shot.png" >
		</SpriteComponent>

		<ItemActionComponent
			_tags="enabled_in_world"
			action_id="DECELERATING_SHOT" >
		</ItemActionComponent>
	</Base>

	<InheritTransformComponent
		_tags="enabled_in_world,enabled_hand"
		parent_hotspot_tag="shoot_pos" >
	</InheritTransformComponent>

	<ParticleEmitterComponent
		_tags="enabled_in_hand,item_identified"
		emitted_material_name="spark_red"
		offset.x="0"
		offset.y="0"
		x_pos_offset_min="-3"
		x_pos_offset_max="3"
		y_pos_offset_min="1"
		y_pos_offset_max="-1"
		x_vel_min="-10"
		x_vel_max="10"
		y_vel_min="-20"
		y_vel_max="-10"
		count_min="1"
		count_max="1"
		lifetime_min="0.4"
		lifetime_max="0.5"
		create_real_particles="0"
		emit_cosmetic_particles="1"
		emission_interval_min_frames="20"
		emission_interval_max_frames="32"
		is_emitting="1" >
	</ParticleEmitterComponent>

</Entity>
```

### Key Components and Attributes

*   **`<Base file="data/entities/base_custom_card.xml">`**:
    *   This indicates the entity inherits functionality and properties from the standard custom card base.

*   **`<SpriteComponent>`**:
    *   `image_file`: Specifies the UI sprite used to represent this card.
        *   `data/ui_gfx/gun_actions/decelerating_shot.png`

*   **`<ItemActionComponent>`**:
    *   `_tags`: Defines when this action is active. `enabled_in_world` means it's usable when the item is in the game world.
    *   `action_id`: A unique identifier for this action.
        *   `DECELERATING_SHOT`

*   **`<InheritTransformComponent>`**:
    *   `_tags`: Controls the visibility and activation state. `enabled_in_world` and `enabled_in_hand` mean it's active when in the world and held by the player.
    *   `parent_hotspot_tag`: Links the card's position to the `shoot_pos` hotspot of its parent (typically the wand).

*   **`<ParticleEmitterComponent>`**:
    *   This component generates cosmetic particles when the item is held and identified.
    *   `_tags`: `enabled_in_hand` and `item_identified` control when particles are emitted.
    *   `emitted_material_name`: The type of particle to emit.
        *   `spark_red`
    *   `offset.x`, `offset.y`: The base position offset for particle emission.
    *   `x_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_min`, `y_pos_offset_max`: Defines a rectangular area for particle spawning.
    *   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Sets the velocity range for emitted particles.
    *   `count_min`, `count_max`: The number of particles emitted per burst.
    *   `lifetime_min`, `lifetime_max`: The duration each particle exists.
    *   `create_real_particles`: Set to `0` to emit cosmetic particles only, not physics-based ones.
    *   `emit_cosmetic_particles`: Set to `1` to enable cosmetic particle emission.
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the timing between particle emission bursts.
    *   `is_emitting`: Set to `1` to ensure particles are emitted.