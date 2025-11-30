---
title: Invisible Scavenger Entity
category: entities
---

# Invisible Scavenger Entity

This document details the configuration for the "Invisible Scavenger" entity in Noita, focusing on its AI, combat, and physical attributes.

## Core Attributes

The Invisible Scavenger is a flying enemy with a focus on ranged attacks and evasion.

### `Entity`

*   **`name`**: `$animal_scavenger_invis` - Unique identifier for this entity.

### `Base` (Inherited from `base_enemy_flying.xml`)

This section outlines the core behaviors and components inherited from a generic flying enemy.

#### `ItemChestComponent`

*   **`level`**: `2` - Indicates the loot tier or quality of items this creature might drop.

#### `AnimalAIComponent`

This component governs the creature's behavior, including detection, combat, and movement.

*   **`_enabled`**: `1` - Enables the AI component.
*   **`preferred_job`**: `JobDefault` - The default job assigned to this creature.
*   **`escape_if_damaged_probability`**: `100` - The creature will always attempt to flee when damaged.
*   **`attack_if_damaged_probability`**: `0` - The creature will never counter-attack when damaged.
*   **`tries_to_ranged_attack_friends`**: `1` - The creature may attempt to use ranged attacks on its allies.
*   **`attack_melee_damage_min`**: `0.4` - Minimum damage for melee attacks (though melee is disabled).
*   **`attack_melee_damage_max`**: `0.7` - Maximum damage for melee attacks (though melee is disabled).
*   **`creature_detection_range_x`**: `400` - Horizontal range for detecting other creatures.
*   **`creature_detection_range_y`**: `400` - Vertical range for detecting other creatures.
*   **`creature_detection_angular_range_deg`**: `60` - The angular field of view for creature detection.
*   **`attack_melee_max_distance`**: `10` - Maximum distance for melee attacks (effectively disabled due to `attack_melee_enabled="0"`).
*   **`food_material`**: `meat` - The material type associated with its food.
*   **`needs_food`**: `0` - This creature does not require food.
*   **`sense_creatures`**: `1` - The creature can sense other creatures.
*   **`can_fly`**: `1` - The creature is capable of flight.
*   **`attack_melee_enabled`**: `0` - Melee attacks are disabled for this creature.
*   **`attack_landing_ranged_enabled`**: `1` - Can perform ranged attacks while landing.
*   **`attack_ranged_enabled`**: `1` - Ranged attacks are enabled.
*   **`attack_ranged_action_frame`**: `1` - The frame at which the ranged attack animation occurs.
*   **`attack_ranged_min_distance`**: `0` - Minimum distance for ranged attacks.
*   **`attack_ranged_max_distance`**: `260` - Maximum distance for ranged attacks.
*   **`attack_ranged_entity_file`**: `data/entities/projectiles/invisshot.xml` - The projectile entity used for ranged attacks.
*   **`attack_ranged_entity_count_min`**: `1` - Minimum number of projectiles fired per attack.
*   **`attack_ranged_entity_count_max`**: `1` - Maximum number of projectiles fired per attack.
*   **`attack_ranged_frames_between`**: `30` - Frames to wait between ranged attacks.
*   **`attack_ranged_offset_x`**: `7` - Horizontal offset for projectile origin.
*   **`attack_ranged_offset_y`**: `-6.8` - Vertical offset for projectile origin.
*   **`aggressiveness_min`**: `90` - Minimum aggressiveness level.
*   **`aggressiveness_max`**: `100` - Maximum aggressiveness level.

#### `DamageModelComponent`

Defines the creature's health and how it reacts to damage.

*   **`hp`**: `1.5` - The creature's hit points.
*   **`materials_create_messages`**: `1` - When damaged, it creates messages related to material interaction.
*   **`ragdoll_filenames_file`**: `data/ragdolls/scavenger_invis/filenames.txt` - Specifies the files for its ragdoll physics.
*   **`fire_probability_of_ignition`**: `5` - 5% chance to ignite when taking damage.
*   **`blood_spray_material`**: `blood` - The material used for blood effects.

#### `SpriteComponent`

Controls the visual representation of the creature.

*   **`image_file`**: `data/enemies_gfx/scavenger_invis.xml` - Path to the sprite definition file.
*   **`offset_x`**: `0` - Horizontal offset for the sprite.
*   **`offset_y`**: `0` - Vertical offset for the sprite.

#### `PathFindingComponent`

Determines how the creature navigates the game world.

*   **`can_jump`**: `0` - Cannot jump.
*   **`can_fly`**: `1` - Can fly.
*   **`jump_speed`**: `80` - Speed when jumping (not used as `can_jump` is 0).
*   **`initial_jump_lob`**: `1` - Initial lob height for jumps (not used).
*   **`initial_jump_max_distance_x`**: `60` - Max horizontal jump distance (not used).
*   **`initial_jump_max_distance_y`**: `60` - Max vertical jump distance (not used).

#### `PathFindingGridMarkerComponent`

Used for pathfinding grid manipulation.

*   **`marker_work_flag`**: `24` - A flag used for pathfinding grid operations.

#### `GenomeDataComponent`

Defines genetic traits and ecological role.

*   **`herd_id`**: `healer` - Identifies its herd or group affiliation.
*   **`food_chain_rank`**: `9` - Its position in the food chain.
*   **`is_predator`**: `1` - This creature is a predator.

#### `CharacterPlatformingComponent`

Governs movement mechanics for characters.

*   **`fly_speed_change_spd`**: `0.8` - Speed modifier for flying.
*   **`fly_velocity_x`**: `28` - Horizontal velocity when flying.
*   **`accel_x`**: `0.03` - Horizontal acceleration.
*   **`jump_velocity_y`**: `-12` - Vertical velocity when jumping (not used).
*   **`run_velocity`**: `17` - Horizontal running speed (not used as it flies).

#### `CameraBoundComponent`

Manages the entity's visibility and interaction with the camera.

*   **`max_count`**: `30` - Maximum number of this entity that can be active within camera bounds.
*   **`distance`**: `160000` - The distance from the camera within which the entity is considered active.

#### `HitboxComponent`

Defines the collision area for the entity.

*   **`aabb_min_x`**: `-5` - Minimum X-coordinate of the bounding box.
*   **`aabb_max_x`**: `5` - Maximum X-coordinate of the bounding box.
*   **`aabb_min_y`**: `-12` - Minimum Y-coordinate of the bounding box.
*   **`aabb_max_y`**: `3` - Maximum Y-coordinate of the bounding box.

#### `CharacterDataComponent`

General character properties.

*   **`collision_aabb_min_x`**: `-2.0` - Minimum X-coordinate for physics collision.
*   **`collision_aabb_max_x`**: `2.0` - Maximum X-coordinate for physics collision.
*   **`collision_aabb_min_y`**: `-3` - Minimum Y-coordinate for physics collision.
*   **`collision_aabb_max_y`**: `3` - Maximum Y-coordinate for physics collision.
*   **`mass`**: `1.1` - The mass of the entity.

### `Base` (Inherited from `base_jetpack.xml`)

This indicates the entity also inherits properties from a jetpack base, likely contributing to its flying capabilities.

### `LightComponent`

Adds a light source to the entity.

*   **`_enabled`**: `1` - Enables the light component.
*   **`radius`**: `50` - The radius of the light.
*   **`fade_out_time`**: `1.5` - Time it takes for the light to fade out.

### `ItemPickUpperComponent`

Allows the entity to pick up items.

*   **`is_in_npc`**: `1` - Indicates it's part of an NPC (Non-Player Character).

### `AudioComponent`

Manages the sound effects for the entity.

*   **`file`**: `data/audio/Desktop/animals.bank` - The audio bank file.
*   **`event_root`**: `animals/scavenger` - The root event name for scavenger sounds.