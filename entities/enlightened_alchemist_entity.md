---
title: Enlightened Alchemist Entity
category: entities
---

# Enlightened Alchemist Entity

This document details the configuration of the "Enlightened Alchemist" entity in Noita, focusing on its AI, visual representation, and combat capabilities.

## Core Attributes

The Enlightened Alchemist is a flying, creature-sensing enemy with ranged attack capabilities. It does not require food and has a specific detection range for other creatures.

### `AnimalAIComponent`

This component governs the creature's behavior and combat.

| Attribute                     | Value                                       | Description                                                                 |
| :---------------------------- | :------------------------------------------ | :-------------------------------------------------------------------------- |
| `preferred_job`               | `JobDefault`                                | Default job assigned to the AI.                                             |
| `attack_melee_enabled`        | `0`                                         | Melee attacks are disabled.                                                 |
| `creature_detection_range_x`  | `400`                                       | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`  | `400`                                       | Vertical range for detecting creatures.                                     |
| `food_material`               | `blood`                                     | The material it consumes for sustenance (though `needs_food` is 0).         |
| `needs_food`                  | `0`                                         | The creature does not require food.                                         |
| `sense_creatures`             | `1`                                         | The creature actively senses other creatures.                               |
| `attack_ranged_enabled`       | `1`                                         | Ranged attacks are enabled.                                                 |
| `can_fly`                     | `1`                                         | The creature is capable of flight.                                          |
| `attack_ranged_entity_file`   | `data/entities/projectiles/enlightened_laser_dark_wand.xml` | The projectile entity used for ranged attacks.                              |
| `attack_ranged_action_frame`  | `4`                                         | The frame at which the ranged attack animation is triggered.                |
| `attack_ranged_frames_between`| `120`                                       | The number of frames between consecutive ranged attacks.                    |
| `attack_ranged_min_distance`  | `300`                                       | The minimum distance from the target to initiate a ranged attack.           |

### `SpriteComponent`

Defines the visual appearance of the Enlightened Alchemist.

| Attribute     | Value                                     | Description                                                                 |
| :------------ | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `image_file`  | `data/enemies_gfx/enlightened_alchemist.xml` | The XML file defining the sprite's appearance and animations.               |
| `alpha`       | `0.5`                                     | The transparency level of the sprite.                                       |
| `offset_x`    | `0`                                       | Horizontal offset of the sprite.                                            |
| `offset_y`    | `0`                                       | Vertical offset of the sprite.                                              |

### `PathFindingComponent`

Configures how the entity navigates the game world.

| Attribute   | Value | Description                                     |
| :---------- | :---- | :---------------------------------------------- |
| `can_jump`  | `0`   | The entity cannot jump.                         |
| `can_walk`  | `0`   | The entity cannot walk.                         |
| `can_fly`   | `1`   | The entity is capable of flying.                |

### `CharacterDataComponent`

Defines physical properties and collision bounds.

| Attribute             | Value   | Description                                     |
| :-------------------- | :------ | :---------------------------------------------- |
| `collision_aabb_min_x`| `-9.0`  | Minimum X-coordinate of the collision bounding box. |
| `collision_aabb_max_x`| `9.0`   | Maximum X-coordinate of the collision bounding box. |
| `collision_aabb_min_y`| `-25`   | Minimum Y-coordinate of the collision bounding box. |
| `collision_aabb_max_y`| `3`     | Maximum Y-coordinate of the collision bounding box. |
| `mass`                | `1.8`   | The mass of the entity.                         |

## Other Notable Components

*   **`ItemChestComponent`**: Indicates that this entity can drop items upon defeat (level 2).
*   **`GenomeDataComponent`**: Assigns a `herd_id` of "ghost", a `food_chain_rank` of 6, and marks it as a predator.
*   **`CameraBoundComponent`**: Manages how the entity interacts with the camera's view, with a `max_count` of 30 and a `distance` of 160000.
*   **`AudioLoopComponent`**: Plays a looping sound effect for the creature's movement.
*   **`AudioComponent`**: Manages general sound events for the creature.
*   **`SpriteComponent` (second instance)**: Defines a special emissive sprite with transparency for a halo effect.
*   **`LuaComponent` (initialization)**: Executes `data/scripts/animals/enlightened_alchemist_init.lua` once upon entity creation.
*   **`LifetimeComponent`**: Sets the entity's lifespan to 600 frames.
*   **`LuaComponent` (disappear)**: Executes `data/scripts/animals/illusion_disappear.lua` when the entity is removed, likely for a vanishing effect.

---
```xml
<Entity tags="glue_NOT" name="$animal_enlightened_alchemist" >
	<Base file="data/entities/base_enemy_basic.xml" >
		<ItemChestComponent level="2" > </ItemChestComponent>
		<AnimalAIComponent 
			preferred_job="JobDefault"
			attack_melee_enabled="0"
			creature_detection_range_x="400"
			creature_detection_range_y="400"
			food_material="blood"
			needs_food="0"
			sense_creatures="1"
			attack_ranged_enabled="1"
			can_fly="1" 
			attack_ranged_entity_file="data/entities/projectiles/enlightened_laser_dark_wand.xml"
			attack_ranged_action_frame="4"
			attack_ranged_frames_between="120"
			attack_ranged_offset_x="12"
			attack_ranged_offset_y="-12"
			attack_ranged_min_distance="0"
			attack_ranged_min_distance="300"
			>
		</AnimalAIComponent>
		<DamageModelComponent 
            _enabled="0"
			>
		</DamageModelComponent>
		<SpriteComponent 
			image_file="data/enemies_gfx/enlightened_alchemist.xml"
			alpha="0.5"
			offset_x="0"
			offset_y="0">
		</SpriteComponent>
		<PathFindingComponent
			can_jump="0" 
			can_walk="0"
			can_fly="1"
			>
		</PathFindingComponent>
		<PathFindingGridMarkerComponent
			marker_work_flag="16" >
		</PathFindingGridMarkerComponent>
		<GenomeDataComponent 
			herd_id="ghost"
			food_chain_rank="6"
			is_predator="1" >
		</GenomeDataComponent>
		<CharacterPlatformingComponent 
			jump_velocity_y="-12" 
			swim_idle_buoyancy_coeff="1.0"
			run_velocity="1"  >
		</CharacterPlatformingComponent>
		<CameraBoundComponent
			max_count="30"
			distance="160000">
		</CameraBoundComponent>
		<HitboxComponent 
            _enabled="0"
			>
        </HitboxComponent>
		<CharacterDataComponent
			collision_aabb_min_x="-9.0" 
			collision_aabb_max_x="9.0" 
			collision_aabb_min_y="-25" 
			collision_aabb_max_y="3"
			mass="1.8" >
		</CharacterDataComponent>
	</Base>
	<AudioLoopComponent
		file="data/audio/Desktop/animals.bank"
		event_name="animals/enlightened_alchemist/movement_loop"
		set_speed_parameter="1"
		auto_play="1">
	</AudioLoopComponent>
	<AudioComponent
		file="data/audio/Desktop/animals.bank"
		event_root="animals/enlightened_alchemist" >
	</AudioComponent>
	<SpriteComponent 
		alpha="0" 
		image_file="data/particles/enlightened_alchemist_halo_dark.xml"
		emissive="1"
        additive="1"
		special_scale_x="1"
		has_special_scale="1"
		rect_animation="stand" >
	</SpriteComponent>
	<LuaComponent
		script_source_file="data/scripts/animals/enlightened_alchemist_init.lua"
		remove_after_executed="1"
		>
	</LuaComponent>
	<LifetimeComponent
		lifetime="600"
		>
	</LifetimeComponent>
	<AudioComponent
		file="data/audio/Desktop/animals.bank"
		event_root="animals/illusion">
	</AudioComponent>
    <LuaComponent
		script_source_file="data/scripts/animals/illusion_disappear.lua"
		execute_every_n_frame="-1"
		execute_on_removed="1"
		>
	</LuaComponent>
</Entity>
```