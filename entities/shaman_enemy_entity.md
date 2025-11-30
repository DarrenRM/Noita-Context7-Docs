---
title: Shaman Enemy Entity
category: entities
---

# Shaman Enemy Entity

This document details the configuration of the Shaman enemy entity in Noita, focusing on its AI, combat, and visual properties.

## Core Entity Configuration

The Shaman is an enemy entity with specific AI behaviors and combat capabilities.

```xml
<Entity tags="shaman,glue_NOT" name="$animal_shaman">
	<Base file="data/entities/base_enemy_basic.xml" >
		<!-- ... other components ... -->
	</Base>
	<!-- ... other components ... -->
</Entity>
```

## Key Components and Attributes

### AnimalAIComponent

This component governs the Shaman's artificial intelligence, including its movement, detection, and attack patterns.

| Attribute                       | Value                               | Description                                                                 |
| :------------------------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `can_fly`                       | `0`                                 | The Shaman cannot fly.                                                      |
| `preferred_job`                 | `JobDefault`                        | Uses the default AI job.                                                    |
| `escape_if_damaged_probability` | `35`                                | 35% chance to attempt to escape when damaged.                               |
| `creature_detection_range_x`    | `250`                               | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`    | `250`                               | Vertical range for detecting creatures.                                     |
| `sense_creatures`               | `1`                                 | Actively senses nearby creatures.                                           |
| `attack_melee_enabled`          | `0`                                 | Melee attacks are disabled.                                                 |
| `attack_ranged_enabled`         | `1`                                 | Ranged attacks are enabled.                                                 |
| `attack_ranged_min_distance`    | `20`                                | Minimum distance to engage in ranged attacks.                               |
| `attack_ranged_max_distance`    | `200`                               | Maximum distance for ranged attacks.                                        |
| `attack_ranged_entity_file`     | `data/entities/projectiles/orb_cursed.xml` | The projectile entity used for ranged attacks.                              |
| `attack_ranged_entity_count_min`| `2`                                 | Minimum number of projectiles fired per attack.                             |
| `attack_ranged_entity_count_max`| `2`                                 | Maximum number of projectiles fired per attack.                             |
| `attack_ranged_state_duration_frames` | `90`                            | Duration of the attack state in frames.                                     |
| `attack_ranged_frames_between`  | `150`                               | Frames to wait between ranged attacks.                                      |
| `attack_ranged_action_frame`    | `10`                                | Frame within the attack state when the projectile is fired.                 |
| `attack_ranged_offset_y`        | `-11`                               | Vertical offset for projectile origin.                                      |
| `attack_ranged_offset_x`        | `8`                                 | Horizontal offset for projectile origin.                                    |

### SpriteComponent

Defines the visual appearance of the Shaman.

| Attribute    | Value                               | Description                               |
| :----------- | :---------------------------------- | :---------------------------------------- |
| `image_file` | `data/enemies_gfx/shaman.xml`       | The sprite sheet for the Shaman.          |
| `alpha`      | `0.5`                               | The Shaman is semi-transparent.           |
| `offset_x`   | `0`                                 | Horizontal sprite offset.                 |
| `offset_y`   | `0`                                 | Vertical sprite offset.                   |

### PathFindingComponent

Controls the Shaman's movement and pathfinding capabilities.

| Attribute                     | Value | Description                                     |
| :---------------------------- | :---- | :---------------------------------------------- |
| `distance_to_reach_node_x`    | `20`  | Horizontal distance to consider a node reached. |
| `distance_to_reach_node_y`    | `20`  | Vertical distance to consider a node reached.   |
| `can_swim_on_surface`         | `1`   | Can swim on the surface of liquids.             |
| `can_dive`                    | `1`   | Can dive into liquids.                          |
| `frames_to_get_stuck`         | `30`  | Frames before considering pathfinding stuck.    |
| `can_jump`                    | `1`   | Can jump.                                       |
| `jump_speed`                  | `80`  | Speed of jumps.                                 |
| `initial_jump_max_distance_x` | `40`  | Maximum horizontal jump distance.               |
| `initial_jump_max_distance_y` | `20`  | Maximum vertical jump distance.                 |

### CharacterPlatformingComponent

Handles character-specific platforming mechanics like gravity and velocity.

| Attribute                               | Value | Description                               |
| :-------------------------------------- | :---- | :---------------------------------------- |
| `pixel_gravity`                         | `600` | The strength of gravity.                  |
| `jump_velocity_y`                       | `-20` | Initial vertical velocity when jumping.   |
| `run_velocity`                          | `12`  | Horizontal movement speed.                |
| `run_animation_velocity_switching_enabled`| `1`   | Enables switching run animations.         |
| `run_animation_velocity_switching_threshold`| `50`  | Threshold for switching run animations. |

### GenomeDataComponent

Provides genetic information for the Shaman, influencing its behavior within herds.

| Attribute           | Value   | Description                               |
| :------------------ | :------ | :---------------------------------------- |
| `herd_id`           | `ghost` | The herd identifier for this creature.    |
| `food_chain_rank`   | `10`    | Its position in the food chain.           |

### CharacterDataComponent

Defines basic character properties like collision and mass.

| Attribute            | Value | Description                               |
| :------------------- | :---- | :---------------------------------------- |
| `collision_aabb_min_x` | `-2.0`| Minimum X-axis for collision bounding box.|
| `collision_aabb_max_x` | `2.0` | Maximum X-axis for collision bounding box.|
| `collision_aabb_min_y` | `-10` | Minimum Y-axis for collision bounding box.|
| `collision_aabb_max_y` | `0`   | Maximum Y-axis for collision bounding box.|
| `mass`               | `1.0` | The mass of the character.                |

## Attached Entities: Shaman's Lantern

The Shaman entity has an attached "lantern" entity, which is a visual and functional element.

### Lantern Sprite and Light

The lantern has its own sprite and emits light.

```xml
	<Entity>
		<InheritTransformComponent
			only_position="1"
			parent_hotspot_tag="hand_hotspot" >
		</InheritTransformComponent>

		<VelocityComponent></VelocityComponent>
		
		<SpriteComponent 
			image_file="data/enemies_gfx/shaman_lantern.png"
			offset_x="3.5"
			offset_y="1"
			alpha="0.5"
			z_index="-1.1">
		</SpriteComponent>
		
		<LightComponent 
			r="30"
			g="255"
			b="30"
			radius="120" >
		</LightComponent>
		<!-- ... particle emitters ... -->
	</Entity>
```

### Lantern Lua Script

The lantern's behavior is controlled by a Lua script.

```xml
		<LuaComponent
			script_source_file="data/scripts/animals/shaman_lantern.lua">
		</LuaComponent>
```

## Visual Effects and Audio

### Particle Emitters

The Shaman utilizes particle emitters for visual effects.

*   **Water Fading:** Used for a fading water effect, likely when the Shaman is damaged or disappears.
    *   `emitted_material_name`: `water_fading`
    *   `lifetime_min`/`max`: `0.1` to `0.3`
    *   `y_vel_min`/`max`: `-5` to `-50` (indicates upward movement)
*   **Lantern Particles:** The lantern itself emits steam and green sparks.
    *   `emitted_material_name`: `steam`, `spark_green`
    *   Various offsets, velocities, and lifetimes for different effects.

### Audio Components

The Shaman has audio events associated with its actions and nature.

*   **Animal Sounds:**
    *   `file`: `data/audio/Desktop/animals.bank`
    *   `event_root`: `animals/shaman`
*   **Illusion Sounds:**
    *   `file`: `data/audio/Desktop/animals.bank`
    *   `event_root`: `animals/illusion`

## Special Behaviors

### Illusion Disappear Script

The Shaman has a script that handles its disappearance, likely as part of its illusionary nature.

```xml
	<LuaComponent
		script_source_file="data/scripts/animals/illusion_disappear.lua"
		execute_every_n_frame="-1"
		execute_on_removed="1"
		>
	</LuaComponent>
```

*   `execute_on_removed="1"`: This script runs when the entity is removed from the game.
*   `execute_every_n_frame="-1"`: This indicates the script is not intended to run on a fixed frame interval but rather on specific events.

### Lifetime Component

The Shaman has a limited lifespan.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `600` | The entity will exist for 600 frames.     |