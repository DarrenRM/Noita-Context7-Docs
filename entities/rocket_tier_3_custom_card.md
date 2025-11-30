---
title: Rocket Tier 3 Custom Card
category: entities
---

---

# Rocket Tier 3 Custom Card

This document details the configuration for the "Rocket Tier 3" custom card entity in Noita, intended for AI-assisted modding.

## Core Entity Configuration

The `Entity` tag defines the root of this custom card.

```xml
<Entity>
	<!-- ... other components ... -->
</Entity>
```

## Base Configuration

The `Base` component inherits from `base_custom_card.xml`, providing fundamental properties for custom cards.

```xml
<Base file="data/entities/base_custom_card.xml">
	<SpriteComponent
		image_file="data/ui_gfx/gun_actions/rocket_tier_3.png">
	</SpriteComponent>
	<ItemActionComponent
		_tags="enabled_in_world"
		action_id="ROCKET_TIER_3">
	</ItemActionComponent>
</Base>
```

*   **`SpriteComponent`**:
    *   `image_file`: Specifies the UI icon for this card (`data/ui_gfx/gun_actions/rocket_tier_3.png`).
*   **`ItemActionComponent`**:
    *   `action_id`: Assigns a unique identifier for this action (`ROCKET_TIER_3`).

## Transform Component

The `InheritTransformComponent` dictates how the card's visual representation is positioned when held.

```xml
<InheritTransformComponent
	_tags="enabled_in_world,enabled_in_hand"
	parent_hotspot_tag="shoot_pos">
</InheritTransformComponent>
```

*   **`parent_hotspot_tag`**: The card will align its visual origin to the `shoot_pos` hotspot of its parent (e.g., the player's wand).

## Particle Emitter Component

This component adds cosmetic visual effects when the card is held.

```xml
<ParticleEmitterComponent
	_tags="enabled_in_hand,item_identified"
	emitted_material_name="spark_purple_bright"
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
	is_emitting="1">
</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: The type of particle to emit (`spark_purple_bright`).
*   **`offset` / `x_pos_offset` / `y_pos_offset`**: Defines the area around the card where particles can spawn.
*   **`x_vel` / `y_vel`**: Controls the initial velocity of the emitted particles.
*   **`lifetime`**: Duration each particle exists.
*   **`create_real_particles`**: Set to `0` to prevent these from interacting physically.
*   **`emit_cosmetic_particles`**: Set to `1` for visual effects only.
*   **`emission_interval`**: Controls the frequency of particle emission.

## Light Component

This component adds a subtle light effect when the card is held.

```xml
<LightComponent
	_tags="enabled_in_hand,item_identified"
	_enabled="1"
	radius="30"
	fade_out_time="1.5"
	r="70"
	g="120"
	b="5">
</LightComponent>
```

*   **`radius`**: The range of the light.
*   **`fade_out_time`**: How long the light takes to fade.
*   **`r`, `g`, `b`**: RGB color values for the light (a greenish-yellow hue).