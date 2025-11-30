---
title: Test Walk Enemy
category: entities
---

# Test Walk Enemy

This document details the configuration for a basic enemy entity in Noita, referred to as "Test Walk". It inherits from a base enemy and defines its AI, combat capabilities, visual representation, and movement properties.

## Key Components and Attributes

### Base Entity Inheritance

The entity inherits core functionality from `data/entities/base_enemy_basic.xml`.

### AnimalAIComponent

This component governs the creature's behavior and AI.

*   **`preferred_job`**: `JobDefault` - Indicates the default job assigned to this creature.
*   **`escape_if_damaged_probability`**: `40` - The percentage chance the creature will attempt to flee when damaged.
*   **`attack_melee_damage_min`**: `0.4` - Minimum damage dealt by melee attacks.
*   **`attack_melee_damage_max`**: `0.7` - Maximum damage dealt by melee attacks.
*   **`creature_detection_range_x`**: `400` - Horizontal range for detecting creatures.
*   **`creature_detection_range_y`**: `400` - Vertical range for detecting creatures.
*   **`creature_detection_angular_range_deg`**: `60` - Angular range (in degrees) for creature detection.
*   **`attack_melee_max_distance`**: `20` - Maximum distance for performing a melee attack.
*   **`food_material`**: `meat` - The material type this creature consumes for sustenance.
*   **`needs_food`**: `1` - Enables the food consumption mechanic for this creature.
*   **`sense_creatures`**: `1` - Enables the creature to sense other creatures.
*   **`attack_ranged_enabled`**: `0` - Disables ranged attacks for this entity.
*   **`attack_melee_enabled`**: `0` - Disables melee attacks for this entity.
*   **`can_fly`**: `0` - The creature cannot fly.
*   **`attack_ranged_action_frame`**: `4` - The animation frame at which a ranged attack is initiated.
*   **`attack_ranged_min_distance`**: `0` - Minimum distance for a ranged attack.
*   **`attack_ranged_max_distance`**: `220` - Maximum distance for a ranged attack.
*   **`attack_ranged_entity_file`**: `data/entities/projectiles/buckshot.xml` - The projectile entity file used for ranged attacks.
*   **`attack_ranged_entity_count_min`**: `3` - Minimum number of projectiles fired per ranged attack.
*   **`attack_ranged_entity_count_max`**: `4` - Maximum number of projectiles fired per ranged attack.
*   **`attack_ranged_frames_between`**: `100` - Frames to wait between ranged attacks.
*   **`attack_ranged_offset_y`**: `-7` - Vertical offset for the origin of ranged attacks.

### DamageModelComponent

Defines how the entity takes damage and its resistances.

*   **`hp`**: `1.1` - The entity's hit points.
*   **`materials_create_messages`**: `1` - Enables messages when specific materials interact with the entity.
*   **`ragdoll_filenames_file`**: `data/ragdolls/shotgunner/filenames.txt` - Specifies the file containing ragdoll animation names.
*   **`fire_probability_of_ignition`**: `5` - The percentage chance the entity will ignite when exposed to fire.
*   **`materials_that_damage`**: `acid,radioactive_liquid,lava,poison` - A list of materials that inflict damage.
*   **`materials_how_much_damage`**: `0.0005,0.000001,0.00003,0.0001` - The damage multiplier for each material listed in `materials_that_damage`.

### SpriteComponent

Determines the visual appearance of the entity.

*   **`image_file`**: `data/enemies_gfx/shotgunner.xml` - The XML file defining the sprite's appearance and animations.
*   **`offset_x`**: `7` - Horizontal offset for the sprite.
*   **`offset_y`**: `14` - Vertical offset for the sprite.

### PathFindingComponent

Configures the entity's pathfinding and movement capabilities.

*   **`can_jump`**: `1` - The entity can jump.
*   **`can_fly`**: `0` - The entity cannot fly.
*   **`jump_speed`**: `80` - The speed at which the entity jumps.
*   **`initial_jump_lob`**: `1` - Controls the arc of the initial jump.
*   **`frames_to_get_stuck`**: `120` - Frames before the entity is considered stuck.
*   **`frames_between_searches`**: `120` - Frames between pathfinding searches.
*   **`initial_jump_max_distance_x`**: `60` - Maximum horizontal distance for an initial jump.
*   **`initial_jump_max_distance_y`**: `60` - Maximum vertical distance for an initial jump.
*   **`can_swim_on_surface`**: `1` - The entity can swim on the surface of liquids.
*   **`can_dive`**: `1` - The entity can dive into liquids.

### PathFindingGridMarkerComponent

Used for marking grid positions during pathfinding.

*   **`marker_work_flag`**: `16` - A flag used internally for pathfinding operations.

### GenomeDataComponent

Defines genetic traits and ecological role.

*   **`herd_id`**: `orcs` - Identifies the herd or group this entity belongs to.
*   **`food_chain_rank`**: `9` - Its position in the food chain.
*   **`is_predator`**: `1` - Indicates that this entity is a predator.

### CharacterPlatformingComponent

Handles character-specific platforming mechanics.

*   **`jump_velocity_y`**: `-12` - The vertical velocity applied when jumping.
*   **`run_velocity`**: `11` - The horizontal movement speed.

### CameraBoundComponent

Manages the entity's interaction with the camera's bounds.

*   **`max_count`**: `30` - Maximum number of this entity that can be active within camera bounds.
*   **`distance`**: `160000` - The distance from the camera within which the entity is considered active.

### HitboxComponent

Defines the collision bounding box for the entity.

*   **`aabb_max_x`**: `5` - Maximum X-coordinate of the axis-aligned bounding box.
*   **`aabb_max_y`**: `3` - Maximum Y-coordinate of the axis-aligned bounding box.
*   **`aabb_min_x`**: `-5` - Minimum X-coordinate of the axis-aligned bounding box.
*   **`aabb_min_y`**: `-12` - Minimum Y-coordinate of the axis-aligned bounding box.

### LightComponent

Adds a light source to the entity.

*   **`radius`**: `50` - The radius of the light emitted.
*   **`fade_out_time`**: `1.5` - The time it takes for the light to fade out.

### ItemPickUpperComponent

This component indicates that the item can be picked up by NPCs.

*   **`is_in_npc`**: `1` - The item is intended to be picked up by NPCs.