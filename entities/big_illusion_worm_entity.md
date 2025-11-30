---
title: Big Illusion Worm Entity
category: entities
---

# Big Illusion Worm Entity

This document details the configuration for the "Big Illusion Worm" entity in Noita, focusing on its AI, visual representation, and behavioral components.

## Entity Definition

The core entity definition for the Big Illusion Worm.

```xml
<Entity 
	tags="mortal,hittable,teleportable_NOT,homing_target,enemy,worm,glue_NOT" 
	name="$animal_worm_big"
	>
	<_Transform 
		position.x="0" 
		position.y="0" 
		rotation="0" 
		scale.x="1" 
		scale.y="1" >
	</_Transform>
    <!-- Other components follow -->
</Entity>
```

*   **`tags`**: Defines the entity's properties and interactions. Key tags include:
    *   `mortal`: Can be killed.
    *   `hittable`: Can be damaged.
    *   `enemy`: Hostile to the player.
    *   `worm`: Indicates it's a worm-type entity.
    *   `glue_NOT`: Cannot be glued.
*   **`name`**: `$animal_worm_big` - The internal name for this entity, likely used for localization.

## Worm Component

Controls the physical movement and segmentation of the worm.

```xml
<WormComponent
	acceleration="1.5"
	gravity="0"
	tail_gravity="0"
	part_distance="16"
	ground_check_offset="32"
	hitbox_radius="1"
	target_kill_radius="10"
	target_kill_ragdoll_force="10"
	eat_anim_wait_mult="0.05"
	jump_cam_shake="6" 
	>
</WormComponent>
```

*   **`acceleration`**: How quickly the worm speeds up.
*   **`gravity`**: Gravity applied to the worm's body. Set to `0` for no gravity.
*   **`tail_gravity`**: Gravity applied specifically to the worm's tail segments.
*   **`part_distance`**: The desired distance between individual worm segments.
*   **`ground_check_offset`**: Offset for checking if the worm is on the ground.
*   **`hitbox_radius`**: The radius of the hitbox for each segment.
*   **`target_kill_radius`**: Radius within which the worm can "kill" a target by eating it.
*   **`target_kill_ragdoll_force`**: Force applied to ragdolls when a target is killed.
*   **`jump_cam_shake`**: Intensity of camera shake when the worm jumps.

## Worm AI Component

Manages the worm's behavior, targeting, and movement patterns.

```xml
<WormAIComponent
	speed="4"
	speed_hunt="5"
	direction_adjust_speed="0.003"
	direction_adjust_speed_hunt="0.04"
	hunt_box_radius="256"
	random_target_box_radius="128"
	new_hunt_target_check_every="240"
	new_random_target_check_every="240"
	give_up_area_radius="150"
	give_up_time_frames="250"
	>
</WormAIComponent>
```

*   **`speed`**: Base movement speed.
*   **`speed_hunt`**: Movement speed when actively hunting a target.
*   **`direction_adjust_speed`**: How quickly the worm adjusts its direction.
*   **`direction_adjust_speed_hunt`**: How quickly the worm adjusts its direction when hunting.
*   **`hunt_box_radius`**: The radius around the worm within which it will actively hunt targets.
*   **`random_target_box_radius`**: The radius within which the worm will seek random targets if no primary target is found.
*   **`new_hunt_target_check_every`**: How often (in frames) the AI checks for new hunt targets.
*   **`new_random_target_check_every`**: How often (in frames) the AI checks for new random targets.
*   **`give_up_area_radius`**: Radius within which the worm will give up pursuing a target.
*   **`give_up_time_frames`**: How long (in frames) the worm will pursue a target before giving up.

## Sprite Components

These components define the visual appearance of the Big Illusion Worm. It uses multiple sprite components to render its head, body segments, and tail, with an illusionary effect.

```xml
<!-- Head Sprite -->
<SpriteComponent 
	_enabled="1" 
	alpha="0.5" 
	image_file="data/enemies_gfx/worm_big_head_illusion.xml" 
	rect_animation="eat" 
	next_rect_animation="eat" 
	offset_x="22" 
	offset_y="12" 
	update_transform="0"
	z_index="-0.5"
	>
</SpriteComponent>

<!-- Body Sprites (multiple instances for segmentation) -->
<SpriteComponent 
	_enabled="1" 
	alpha="0.5" 
	image_file="data/enemies_gfx/worm_big_body_illusion.xml" 
	rect_animation="eat" 
	next_rect_animation="eat" 
	offset_x="22" 
	offset_y="12" 
	update_transform="0"
	z_index="-0.4"
	>
</SpriteComponent>
<!-- ... additional body sprites with increasing z_index ... -->

<!-- Tail Sprite -->
<SpriteComponent 
	_enabled="1" 
	alpha="0.5" 
	image_file="data/enemies_gfx/worm_big_tail_illusion.xml" 
	rect_animation="eat" 
	next_rect_animation="" 
	offset_x="22" 
	offset_y="12" 
	update_transform="0"
	z_index="-0.35"
	>
</SpriteComponent>
```

*   **`alpha`**: Set to `0.5` for a semi-transparent, illusionary effect.
*   **`image_file`**: Specifies the graphical asset for each part (head, body, tail).
*   **`rect_animation`**: The animation to play (e.g., "eat").
*   **`z_index`**: Controls the layering of sprites, creating the segmented appearance.
*   **`offset_x`, `offset_y`**: Adjusts the sprite's position relative to its entity origin.

## Sprite Stains Component

These components are associated with each sprite and likely handle visual effects like blood or damage stains.

```xml
<SpriteStainsComponent
	fade_stains_towards_srite_top="0"
	sprite_id="0">
</SpriteStainsComponent>
<!-- ... multiple instances for each sprite ... -->
```

*   **`sprite_id`**: Links the stain component to a specific sprite instance.
*   **`fade_stains_towards_srite_top`**: Controls how stains fade.

## Other Key Components

*   **`DamageModelComponent`**: Although `_enabled="0"`, this component is present and could be enabled to give the worm health and damage properties.
*   **`PathFindingGridMarkerComponent`**: Helps the entity navigate the game's pathfinding grid.
*   **`GenomeDataComponent`**: Defines its place in the ecosystem:
    *   `herd_id="ghost"`: Likely indicates it's part of a "ghost" group.
    *   `food_chain_rank="6"`: Its position in the food chain.
    *   `is_predator="1"`: It hunts other creatures.
*   **`CameraBoundComponent`**: Manages how the camera behaves relative to the worm.
*   **`AudioComponent`**: Handles sound effects for the worm.
*   **`AudioLoopComponent`**: Plays a continuous sound loop for movement.
*   **`LifetimeComponent`**: Sets a duration for the entity's existence.
*   **`LuaComponent`**: Executes a Lua script (`illusion_disappear.lua`) when the entity is removed, likely for its illusionary disappearance effect.