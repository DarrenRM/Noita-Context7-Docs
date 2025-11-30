---
title: Scavenger (Healer) Entity
category: entities
---

# Scavenger (Healer) Entity

This document details the configuration for the "Scavenger (Healer)" entity in Noita, focusing on its AI, combat, and physical attributes.

## Core Attributes

The Scavenger (Healer) is a flying enemy with a focus on ranged healing attacks.

### `Entity`

The root element defining the entity.

*   **`name`**: `$animal_scavenger_heal` - Unique identifier for this entity.

### `Base` (Inheritance)

This entity inherits properties from several base entity files.

*   **`data/entities/base_enemy_flying.xml`**: Provides fundamental flying enemy behaviors.
*   **`data/entities/base_jetpack.xml`**: Likely contributes to its aerial movement capabilities.

## Key Components

### `AnimalAIComponent`

Defines the artificial intelligence and behavior patterns of the Scavenger (Healer).

*   **`_enabled`**: `1` - Enables the AI component.
*   **`preferred_job`**: `JobDefault` - Default job assigned to this creature.
*   **`escape_if_damaged_probability`**: `100` - The creature will always attempt to escape when damaged.
*   **`attack_if_damaged_probability`**: `0` - The creature will never attack when damaged.
*   **`tries_to_ranged_attack_friends`**: `1` - The creature will attempt to use its ranged attack on allies.
*   **`attack_melee_damage_min`**: `0.4` - Minimum damage for melee attacks (though melee is disabled).
*   **`attack_melee_damage_max`**: `0.7` - Maximum damage for melee attacks (though melee is disabled).
*   **`creature_detection_range_x`**: `400` - Horizontal range for detecting creatures.
*   **`creature_detection_range_y`**: `400` - Vertical range for detecting creatures.
*   **`creature_detection_angular_range_deg`**: `60` - Angular range for detecting creatures.
*   **`attack_melee_max_distance`**: `10` - Maximum distance for melee attacks (effectively disabled).
*   **`food_material`**: `meat` - The material it consumes for food.
*   **`needs_food`**: `0` - This creature does not require food.
*   **`sense_creatures`**: `1` - The creature can sense other creatures.
*   **`can_fly`**: `1` - The creature is capable of flight.
*   **`attack_melee_enabled`**: `0` - Melee attacks are disabled.
*   **`attack_landing_ranged_enabled`**: `1` - Can perform ranged attacks while landing.
*   **`attack_ranged_enabled`**: `1` - Ranged attacks are enabled.
*   **`attack_ranged_action_frame`**: `1` - The frame at which the ranged attack animation occurs.
*   **`attack_ranged_min_distance`**: `0` - Minimum distance for ranged attacks.
*   **`attack_ranged_max_distance`**: `220` - Maximum distance for ranged attacks.
*   **`attack_ranged_entity_file`**: `data/entities/projectiles/healshot.xml` - The projectile entity used for ranged attacks (a healing shot).
*   **`attack_ranged_entity_count_min`**: `1` - Minimum number of projectiles fired per attack.
*   **`attack_ranged_entity_count_max`**: `1` - Maximum number of projectiles fired per attack.
*   **`attack_ranged_frames_between`**: `30` - Frames to wait between ranged attacks.
*   **`attack_ranged_offset_x`**: `7` - Horizontal offset for the ranged attack origin.
*   **`attack_ranged_offset_y`**: `-6.8` - Vertical offset for the ranged attack origin.
*   **`aggressiveness_min`**: `90` - Minimum aggressiveness level.
*   **`aggressiveness_max`**: `100` - Maximum aggressiveness level.

### `DamageModelComponent`

Manages the health and damage-related properties of the entity.

*   **`hp`**: `0.7` - The creature's health points.
*   **`materials_create_messages`**: `1` - Creates messages when materials are applied or removed.
*   **`ragdoll_filenames_file`**: `data/ragdolls/scavenger_heal/filenames.txt` - Specifies the ragdoll files for this creature.
*   **`fire_probability_of_ignition`**: `5` - Probability of catching fire.
*   **`blood_spray_material`**: `blood` - The material used for blood spray effects.

### `SpriteComponent`

Defines the visual appearance of the entity.

*   **`image_file`**: `data/enemies_gfx/scavenger_heal.xml` - Path to the sprite's graphical definition.
*   **`offset_x`**: `0` - Horizontal offset for the sprite.
*   **`offset_y`**: `0` - Vertical offset for the sprite.

### `PathFindingComponent`

Handles pathfinding and movement capabilities.

*   **`can_jump`**: `0` - Cannot jump.
*   **`can_fly`**: `1` - Can fly.
*   **`jump_speed`**: `80` - Speed of jumping (not used as `can_jump` is 0).
*   **`initial_jump_lob`**: `1` - Initial lob for jumping (not used).
*   **`initial_jump_max_distance_x`**: `60` - Max horizontal jump distance (not used).
*   **`initial_jump_max_distance_y`**: `60` - Max vertical jump distance (not used).

### `PathFindingGridMarkerComponent`

Used for pathfinding grid manipulation.

*   **`marker_work_flag`**: `24` - Flag used for pathfinding grid marking.

### `GenomeDataComponent`

Contains genetic information and ecological role.

*   **`herd_id`**: `healer` - Identifier for its herd or group.
*   **`food_chain_rank`**: `9` - Its position in the food chain.
*   **`is_predator`**: `1` - This creature is a predator.

### `CharacterPlatformingComponent`

Governs character movement physics.

*   **`fly_speed_change_spd`**: `0.8` - Speed modifier for flight.
*   **`fly_velocity_x`**: `28` - Horizontal velocity during flight.
*   **`accel_x`**: `0.03` - Horizontal acceleration.
*   **`jump_velocity_y`**: `-12` - Vertical velocity when jumping (not used).
*   **`run_velocity`**: `17` - Running speed (not applicable for flying).

### `CameraBoundComponent`

Controls how the entity interacts with the camera's bounds.

*   **`max_count`**: `30` - Maximum number of this entity that can be active within camera bounds.
*   **`distance`**: `160000` - Distance threshold for camera bounding.

### `HitboxComponent`

Defines the collision area for the entity.

*   **`aabb_min_x`**: `-5` - Minimum X-axis coordinate of the bounding box.
*   **`aabb_max_x`**: `5` - Maximum X-axis coordinate of the bounding box.
*   **`aabb_min_y`**: `-12` - Minimum Y-axis coordinate of the bounding box.
*   **`aabb_max_y`**: `3` - Maximum Y-axis coordinate of the bounding box.

### `CharacterDataComponent`

General character data.

*   **`collision_aabb_min_x`**: `-2.0` - Minimum X-axis for collision.
*   **`collision_aabb_max_x`**: `2.0` - Maximum X-axis for collision.
*   **`collision_aabb_min_y`**: `-3` - Minimum Y-axis for collision.
*   **`collision_aabb_max_y`**: `3` - Maximum Y-axis for collision.
*   **`mass`**: `1.1` - The mass of the character.

### `ItemChestComponent`

Indicates that the entity can drop loot.

*   **`level`**: `2` - The loot drop level.

### `LightComponent`

Adds a light source to the entity.

*   **`_enabled`**: `1` - Enables the light component.
*   **`radius`**: `50` - The radius of the light.
*   **`fade_out_time`**: `1.5` - Time it takes for the light to fade out.

### `ItemPickUpperComponent`

Allows the entity to pick up items.

*   **`is_in_npc`**: `1` - Indicates it's part of an NPC interaction.

### `AudioComponent`

Manages sound effects for the entity.

*   **`file`**: `data/audio/Desktop/animals.bank` - The audio bank file.
*   **`event_root`**: `animals/scavenger` - The root event for scavenger sounds.