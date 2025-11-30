---
title: Eel Entity Configuration
category: entities
---

# Eel Entity Configuration

This document details the configuration for the Eel entity in Noita, focusing on its AI, combat, and visual properties.

## Entity Definition

The base entity definition for the Eel.

```xml
<Entity 
	name="$animal_eel" 
	tags="mortal,hittable,homing_target,destruction_target,enemy,glue_NOT" >
	<_Transform 
		position.x="0" 
		position.y="0" 
		rotation="0" 
		scale.x="1" 
		scale.y="1" >
	</_Transform>
</Entity>
```

### Key Tags:

*   `mortal`: The entity can be killed.
*   `hittable`: The entity can be damaged by projectiles.
*   `homing_target`: Can be targeted by homing projectiles.
*   `destruction_target`: Can be destroyed by certain game mechanics.
*   `enemy`: Identifies the entity as an enemy.
*   `glue_NOT`: Indicates it is not affected by glue.

## Worm Component

Defines the physical and movement characteristics of the Eel as a "worm" type entity.

```xml
<WormComponent
	is_water_worm="1"
	acceleration="0.5"
	gravity="4"
	tail_gravity="30"
	part_distance="14"
	ground_check_offset="1"
	hitbox_radius="5"
	target_kill_radius="7"
	target_kill_ragdoll_force="8"
	ragdoll_filename="data/ragdolls/worm/filenames.txt"
	eat_anim_wait_mult="0.1"
	jump_cam_shake="6" 
	>
</WormComponent>
```

### Key Attributes:

*   `is_water_worm`: Set to `1`, indicating it primarily moves in water.
*   `acceleration`: Controls how quickly the Eel reaches its top speed.
*   `gravity`: The gravitational pull affecting the Eel's body segments.
*   `tail_gravity`: The gravitational pull affecting the Eel's tail segments, often higher to keep it grounded.
*   `part_distance`: The spacing between segments of the Eel's body.
*   `hitbox_radius`: The radius of the collision box for damage detection.
*   `ragdoll_filename`: Specifies the file containing the ragdoll configuration for when the Eel dies.

## Worm AI Component

Governs the behavior and targeting logic of the Eel.

```xml
<WormAIComponent
	speed="2"
	speed_hunt="4"
	direction_adjust_speed="0.012"
	direction_adjust_speed_hunt="0.06"
	hunt_box_radius="256"
	random_target_box_radius="128"
	new_hunt_target_check_every="120"
	new_random_target_check_every="120"
	give_up_area_radius="60"
	give_up_time_frames="250"
	>
</WormAIComponent>
```

### Key Attributes:

*   `speed`: The base movement speed of the Eel.
*   `speed_hunt`: The increased speed when actively hunting a target.
*   `direction_adjust_speed`: How quickly the Eel adjusts its direction.
*   `direction_adjust_speed_hunt`: Faster direction adjustment when hunting.
*   `hunt_box_radius`: The radius around the Eel within which it will actively hunt targets.
*   `random_target_box_radius`: The radius within which the Eel will seek random targets if none are found.
*   `new_hunt_target_check_every`: How often (in frames) the AI checks for new hunt targets.
*   `give_up_area_radius`: The radius within which the Eel will give up pursuing a target.
*   `give_up_time_frames`: The duration (in frames) the Eel will pursue a target before giving up.

## Damage Model Component

Defines the health, damage resistances, and damage taken by the Eel.

```xml
<DamageModelComponent 
	_enabled="1" 
	air_needed="0" 
	falling_damages="0" 
	fire_damage_amount="0.2" 
	fire_probability_of_ignition="0.5" 
	blood_material="blood_worm"
	blood_spray_material="blood_worm"
	hp="20" 
	materials_damage="1" 
	materials_that_damage="acid,lava,poison,blood_cold,blood_cold_vapour" 
	materials_how_much_damage="0.004,0.004,0.001,0.0008,0.0007"
	ragdoll_material="meat_worm"
	ragdoll_offset_y="-6"
	>
</DamageModelComponent>
```

### Key Attributes:

*   `hp`: The total health points of the Eel.
*   `fire_damage_amount`: The amount of damage taken from fire per tick.
*   `fire_probability_of_ignition`: The chance of igniting when taking fire damage.
*   `blood_material`: The material used for blood particles when the Eel is hit.
*   `materials_that_damage`: A list of materials that inflict damage on the Eel.
*   `materials_how_much_damage`: The corresponding damage values for each material in `materials_that_damage`.
*   `ragdoll_material`: The material of the ragdoll when the Eel dies.

## Path Finding Grid Marker Component

Used for AI pathfinding, marking the entity's presence on the navigation grid.

```xml
<PathFindingGridMarkerComponent
	marker_offset_y="0"
	marker_work_flag="16" >
</PathFindingGridMarkerComponent>
```

## Genome Data Component

Defines the genetic properties of the Eel, influencing its role in the ecosystem.

```xml
<GenomeDataComponent 
	_enabled="1"
	herd_id="eel"
	food_chain_rank="20"
	is_predator="1" >
</GenomeDataComponent>
```

### Key Attributes:

*   `herd_id`: A unique identifier for the species, used for grouping and AI interactions.
*   `food_chain_rank`: Its position in the food chain (higher numbers are higher up).
*   `is_predator`: Set to `1`, indicating it preys on other creatures.

## Sprite Components

These components define the visual appearance of the Eel, broken down into different body parts.

```xml
<SpriteComponent 
	_enabled="1" 
	alpha="1" 
	image_file="data/enemies_gfx/eel_head.png" 
	offset_x="18" 
	offset_y="10" 
	>
</SpriteComponent>

<SpriteComponent 
	_enabled="1" 
	alpha="1" 
	image_file="data/enemies_gfx/eel_body.png" 
	offset_x="18" 
	offset_y="10" 
	>
</SpriteComponent>

<SpriteComponent 
	_enabled="1" 
	alpha="1" 
	image_file="data/enemies_gfx/eel_body2.png" 
	offset_x="18" 
	offset_y="10" 
	>
</SpriteComponent>

<SpriteComponent 
	_enabled="1" 
	alpha="1" 
	image_file="data/enemies_gfx/eel_body3.png" 
	offset_x="18" 
	offset_y="10" 
	>
</SpriteComponent>

<SpriteComponent 
	_enabled="1" 
	alpha="1" 
	image_file="data/enemies_gfx/eel_tail.png" 
	offset_x="18" 
	offset_x="7" 
	offset_y="10" 
	>
</SpriteComponent>
```

### Key Attributes:

*   `image_file`: The path to the sprite image for each body segment.
*   `offset_x`, `offset_y`: The positional offset of the sprite relative to the entity's origin.

## Camera Bound Component

Determines how the camera behaves in relation to the Eel.

```xml
<CameraBoundComponent
	max_count="10"
	distance="2000">
</CameraBoundComponent>
```

### Key Attributes:

*   `max_count`: Maximum number of this entity type that can be active before camera effects are reduced.
*   `distance`: The maximum distance from the player at which this entity will be rendered or interact.