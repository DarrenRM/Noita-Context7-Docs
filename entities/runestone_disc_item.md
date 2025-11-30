---
title: Runestone Disc Item
category: entities
---

---

# Runestone Disc Item

This document details the configuration for the Runestone Disc item in Noita, focusing on its attributes relevant to AI-assisted modding.

## Core Entity Configuration

The Runestone Disc inherits its base functionality from `runestone_base.xml`.

```xml
<Entity>
	<Base file="data/entities/items/pickup/runestones/runestone_base.xml">
		<!-- ... other components ... -->
	</Base>
</Entity>
```

## Key Components and Attributes

### PhysicsImageShapeComponent

Defines the visual representation of the runestone when it's in the game world.

```xml
<PhysicsImageShapeComponent 
	image_file="data/items_gfx/runestones/runestone_disc.png"
	>
</PhysicsImageShapeComponent>
```

*   **`image_file`**: Specifies the texture used for the runestone's physics shape.

### ItemComponent

Handles the item's identification and UI display.

```xml
<ItemComponent
	item_name="$item_runestone_disc"
	ui_sprite="data/ui_gfx/items/runestone_disc.png"
	ui_description="$itemdesc_runestone"
	>
</ItemComponent>
```

*   **`item_name`**: The internal name for the item, used for referencing.
*   **`ui_sprite`**: The texture displayed in the player's inventory and UI.
*   **`ui_description`**: The text description shown in the UI, likely referencing a localization string.

### UIInfoComponent

Provides information for UI elements, often mirroring `ItemComponent` for consistency.

```xml
<UIInfoComponent
	name="$item_runestone_disc"
	>
</UIInfoComponent>
```

*   **`name`**: The name displayed in UI elements.

### AbilityComponent

Associated with the item's potential abilities or interactions.

```xml
<AbilityComponent
	ui_name="$item_runestone_disc"
	>
</AbilityComponent>
```

*   **`ui_name`**: The name displayed when considering the item's abilities.

### SpriteComponent

Defines the visual appearance of the item when held by the player.

```xml
<SpriteComponent
	image_file="data/items_gfx/in_hand/runestone_disc.png"
	>
</SpriteComponent>
```

*   **`image_file`**: The texture used when the runestone is in the player's hand.

### ParticleEmitterComponent

Responsible for visual effects, specifically a "spark" effect when activated.

```xml
<ParticleEmitterComponent
	_tags="activate"
	_enabled="0"
	emitted_material_name="spark_white"
	lifetime_min="8.01"
	lifetime_max="8.1"
	count_min="100"
	count_max="100"
	render_on_grid="0"
	fade_based_on_lifetime="1"
	area_circle_radius.min="16"
	area_circle_radius.max="16"
	cosmetic_force_create="1"
	airflow_force="0.251"
	airflow_time="1.01"
	airflow_scale="0.05"
	emission_interval_min_frames="20"
	emission_interval_max_frames="20"
	emit_cosmetic_particles="1"
	velocity_always_away_from_center="100"
	collide_with_grid="0"
	>
</ParticleEmitterComponent>
```

*   **`_tags`**: Indicates this component is active when the "activate" tag is present.
*   **`emitted_material_name`**: The type of particle to emit (e.g., "spark\_white").
*   **`lifetime_min`/`lifetime_max`**: Duration of the particle effect.
*   **`count_min`/`count_max`**: Number of particles emitted.
*   **`area_circle_radius.min`/`max`**: The radius of the emission area.
*   **`velocity_always_away_from_center`**: Controls particle direction.

### LuaComponent (Scripting)

This component links to the item's specific Lua script for custom behavior.

```xml
<LuaComponent
	_tags="enabled_in_world,activate"
	script_source_file="data/scripts/items/runestones/runestone_disc.lua"
	execute_every_n_frame="5"
	_enabled="0"
	>
</LuaComponent>
```

*   **`_tags`**: Specifies when the script should be active (e.g., "enabled\_in\_world", "activate").
*   **`script_source_file`**: The path to the Lua script file that defines the item's behavior.
*   **`execute_every_n_frame`**: Controls how often the script's update function is called.