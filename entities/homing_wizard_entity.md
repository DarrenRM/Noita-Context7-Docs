---
title: Homing Wizard Entity
category: entities
---

# Homing Wizard Entity

This document describes the `wizard_homing.xml` entity, a flying enemy that attacks with homing projectiles.

## Key Attributes

### `AnimalAIComponent`

This component governs the creature's behavior and senses.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `creature_detection_range_x` | Horizontal range (in pixels) for detecting creatures.                    |
| `creature_detection_range_y` | Vertical range (in pixels) for detecting creatures.                      |
| `sense_creatures`         | Enables creature detection.                                              |
| `attack_ranged_enabled`   | Enables ranged attacks.                                                  |
| `can_fly`                 | Allows the entity to fly.                                                |
| `attack_ranged_entity_file` | Path to the projectile entity file (`orb_homing.xml`).                   |
| `attack_ranged_frames_between` | Number of frames between ranged attacks.                                 |
| `attack_ranged_max_distance` | Maximum distance (in pixels) for ranged attacks.                         |

### `DamageModelComponent`

Defines the entity's health and damage resistance.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `hp`                      | Hit points of the entity.                                                |
| `ragdoll_material`        | Material used for the ragdoll when the entity is defeated.               |
| `critical_damage_resistance` | Resistance to critical damage.                                           |

### `SpriteComponent`

Determines the visual appearance of the entity.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `image_file`              | Path to the sprite's image file (`wizard_wither.xml`).                   |

### `CharacterPlatformingComponent`

Controls movement capabilities.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `jump_velocity_y`         | Vertical velocity applied when jumping.                                  |
| `run_velocity`            | Horizontal movement speed.                                               |

### `HitboxComponent`

Defines the collision boundaries of the entity.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `aabb_min_x`              | Minimum X-coordinate of the Axis-Aligned Bounding Box.                   |
| `aabb_max_x`              | Maximum X-coordinate of the Axis-Aligned Bounding Box.                   |
| `aabb_min_y`              | Minimum Y-coordinate of the Axis-Aligned Bounding Box.                   |
| `aabb_max_y`              | Maximum Y-coordinate of the Axis-Aligned Bounding Box.                   |

## Other Notable Components

*   **`ItemChestComponent`**: Indicates the entity can drop loot.
*   **`PathFindingComponent`**: Enables pathfinding capabilities.
*   **`GenomeDataComponent`**: Provides genetic information, including `herd_id` and `food_chain_rank`.
*   **`CameraBoundComponent`**: Manages the entity's visibility based on camera distance.
*   **`CharacterDataComponent`**: Defines collision properties for character interactions.
*   **`ItemPickUpperComponent`**: Allows the entity to pick up items.
*   **`HotspotComponent`**: Defines specific points on the entity, like `cape_root`.
*   **`AudioLoopComponent`**: Plays a looping movement sound.
*   **`AudioComponent`**: Manages general sound events for the entity.
*   **`Entity` (for cape)**: Defines a separate entity for the wizard's cape, utilizing `verlet_chains/cape/cape.xml`.
*   **`Entity` (for game effect)**: Applies a `STUN_PROTECTION_FREEZE` game effect.

```xml
<Entity name="$animal_wizard_homing" >
	<Base file="data/entities/base_enemy_basic.xml" >
		<ItemChestComponent level="2" > </ItemChestComponent>
		
		<AnimalAIComponent 
			_enabled="1" 
			preferred_job="JobDefault"
			attack_melee_enabled="0"
			creature_detection_range_x="400"
			creature_detection_range_y="400"
			food_material="blood"
			needs_food="0"
			sense_creatures="1"
			attack_ranged_enabled="1"
			can_fly="1" 
			attack_ranged_entity_file="data/entities/projectiles/orb_homing.xml"
			attack_ranged_action_frame="5"
			attack_ranged_frames_between="120"
			attack_ranged_offset_y="0"
			attack_ranged_min_distance="0"
			attack_ranged_max_distance="300"
			>
		</AnimalAIComponent>
		
		<DamageModelComponent 
            hp="12"
            ragdoll_material="meat_slime"
			ragdoll_filenames_file="data/ragdolls/wizard_wither/filenames.txt"
			critical_damage_resistance="1.0"
			>
		</DamageModelComponent>

		<SpriteComponent 
			image_file="data/enemies_gfx/wizard_wither.xml" 
			offset_x="0"
			offset_y="0"
			>
		</SpriteComponent>

		<PathFindingComponent
			can_jump="1" >
		</PathFindingComponent>

		<PathFindingGridMarkerComponent
			marker_work_flag="16" >
		</PathFindingGridMarkerComponent>
		
		<GenomeDataComponent 
			herd_id="mage"
			food_chain_rank="6"
			is_predator="1" >
		</GenomeDataComponent>
		
		<CharacterPlatformingComponent 
			jump_velocity_y="-8" 
			swim_idle_buoyancy_coeff="1.0"
			run_velocity="12"  >
		</CharacterPlatformingComponent>
		
		<CameraBoundComponent
			max_count="30"
			distance="160000">
		</CameraBoundComponent>
		
		<HitboxComponent 
		  _enabled="1" 
		  aabb_min_x="-4.5" 
		  aabb_max_x="4.5" 
		  aabb_min_y="-10" 
		  aabb_max_y="3" 
		  >
		</HitboxComponent>
		
		<CharacterDataComponent 
			collision_aabb_min_x="-3.0" 
			collision_aabb_max_x="3.0" 
			collision_aabb_min_y="-7" 
			collision_aabb_max_y="3" 
			>
	    </CharacterDataComponent>
	</Base>
	
	<ItemPickUpperComponent
    	is_in_npc="1">
    </ItemPickUpperComponent>
	
	<HotspotComponent
        _tags="cape_root"
        sprite_hotspot_name="cape" >
    </HotspotComponent>
	
	<AudioLoopComponent
		file="data/audio/Desktop/animals.bank"
		event_name="animals/wizard/movement_loop"
		set_speed_parameter="1"
		auto_play="1">
	</AudioLoopComponent>

	<AudioComponent
		file="data/audio/Desktop/animals.bank"
		event_root="animals/wizard" >
	</AudioComponent>

	<Entity name="cape">  
        <Base file="data/entities/verlet_chains/cape/cape.xml">  
        	<VerletPhysicsComponent
        		cloth_color_edge="0xFF97dace"
        		cloth_color="0xFF3271b3">
        	</VerletPhysicsComponent>
        </Base>  
    </Entity>
	
	<Entity>
		<InheritTransformComponent />
		
	    <GameEffectComponent 
	        effect="STUN_PROTECTION_FREEZE"
	        frames="-1"
	    >
		</GameEffectComponent >
	</Entity>
</Entity>
```