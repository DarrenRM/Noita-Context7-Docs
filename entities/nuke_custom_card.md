---
title: Nuke Custom Card
category: entities
---

# Nuke Custom Card

This document describes the "Nuke" custom card entity in Noita, focusing on its key attributes for AI-assisted modding.

## Entity Definition

The Nuke card is a custom entity that functions as a powerful, explosive spell. It inherits from `base_custom_card.xml` and `base_high_explosive.xml` to define its core behavior and visual representation.

### Key Components

*   **Base Entity:**
    *   Inherits from `data/entities/base_custom_card.xml`.
    *   **SpriteComponent:** Defines the visual appearance of the card in the UI.
        *   `image_file`: `data/ui_gfx/gun_actions/nuke.png`
    *   **ItemActionComponent:** Assigns the unique action ID for this card.
        *   `action_id`: `NUKE`

*   **InheritTransformComponent:**
    *   Ensures the card's transform properties are inherited correctly when held.
    *   `parent_hotspot_tag`: `shoot_pos` (indicates where the action originates from when held).

*   **ParticleEmitterComponent:**
    *   Responsible for visual effects when the card is held.
    *   `emitted_material_name`: `spark` (the type of particle emitted).
    *   `x_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_min`, `y_pos_offset_max`: Define the spawn area for particles.
    *   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Control the initial velocity of emitted particles.
    *   `count_min`, `count_max`: Number of particles emitted per burst.
    *   `lifetime_min`, `lifetime_max`: Duration particles exist.
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the rate of particle emission.
    *   `emit_cosmetic_particles`: `1` (indicates these are visual effects, not functional projectiles).

*   **Base High Explosive:**
    *   Inherits from `data/entities/misc/custom_cards/base_high_explosive.xml`. This is crucial as it provides the underlying explosive mechanics for the card.

*   **LightComponent:**
    *   Adds a light source when the card is held, indicating its presence and potentially its power.
    *   `radius`: `30` (the range of the light).
    *   `fade_out_time`: `1.5` (how long the light fades out).
    *   `r`, `g`, `b`: Color values for the light (warm orange/yellow).

```xml
<Entity>
	
	<Base file="data/entities/base_custom_card.xml" > 
		<SpriteComponent 
			image_file="data/ui_gfx/gun_actions/nuke.png" 
			>
		</SpriteComponent>
		
		<ItemActionComponent 
			_tags="enabled_in_world"
			action_id="NUKE" >
		</ItemActionComponent>
	</Base>

	<InheritTransformComponent
		_tags="enabled_in_world,enabled_in_hand"
		parent_hotspot_tag="shoot_pos" >
	</InheritTransformComponent>

	<ParticleEmitterComponent 
		_tags="enabled_in_hand,item_identified"
		emitted_material_name="spark"
		offset.x="0"
		offset.y="0"
		x_pos_offset_min="-2"
		x_pos_offset_max="2"
		y_pos_offset_min="2"
		y_pos_offset_max="-2"
		x_vel_min="-2"
		x_vel_max="2"
		y_vel_min="-20"
		y_vel_max="-10"
		count_min="1"
		count_max="2"
		lifetime_min="0.2"
		lifetime_max="0.3"
		create_real_particles="0"
		emit_cosmetic_particles="1"
		emission_interval_min_frames="8"
		emission_interval_max_frames="15"
		is_emitting="1" >
	</ParticleEmitterComponent>
	
	<Base file="data/entities/misc/custom_cards/base_high_explosive.xml">
	</Base>

	<LightComponent 
    	_tags="enabled_in_hand,item_identified"
        _enabled="1" 
        radius="30"
        fade_out_time="1.5" 
    	r="120"
    	g="70"
    	b="5" >
	</LightComponent>
	
</Entity>
```