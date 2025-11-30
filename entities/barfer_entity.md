---
title: Barfer Entity
category: entities
---

# Barfer Entity

This document details the `barfer.xml` entity, a flying, ranged-attacking creature in Noita.

## Core Components

The Barfer entity is built upon several base components, defining its fundamental behavior and attributes.

### Base Enemy Basic

This is the foundational component for most enemy entities, providing core AI and combat functionalities.

### AnimalAIComponent

This component governs the Barfer's artificial intelligence, including its senses, attack patterns, and movement capabilities.

*   **`creature_detection_range_x` / `creature_detection_range_y`**: Defines the horizontal and vertical range (400 units) at which the Barfer can detect other creatures.
*   **`food_material`**: Specifies the material the creature consumes ("blood").
*   **`needs_food`**: Set to "0", indicating the Barfer does not require food to survive.
*   **`sense_creatures`**: Set to "1", enabling creature detection.
*   **`attack_ranged_enabled`**: Set to "1", allowing ranged attacks.
*   **`can_fly`**: Set to "1", enabling flight.
*   **`attack_ranged_entity_file`**: The projectile used for ranged attacks is defined by `data/entities/projectiles/radioactive_liquid.xml`.
*   **`attack_ranged_action_frame`**: The frame at which the ranged attack is initiated (frame 3).
*   **`attack_ranged_frames_between`**: The number of frames between ranged attacks (100 frames).
*   **`attack_ranged_offset_y`**: Vertical offset for the ranged attack ( -9 units).
*   **`attack_ranged_min_distance`**: The minimum distance required for a ranged attack (50 units).

### DamageModelComponent

Manages the Barfer's health, damage resistances, and visual effects upon taking damage.

*   **`hp`**: The Barfer has 4 hit points.
*   **`ragdoll_material`**: The material used for its ragdoll upon death ("meat_confusion").
*   **`ragdoll_filenames_file`**: Specifies the files used for the Barfer's ragdoll animation (`data/ragdolls/barfer/filenames.txt`).
*   **`blood_sprite_directional`**: Defines the directional blood splatter sprite (`data/particles/bloodsplatters/bloodsplatter_directional_green_$[1-3].xml`).
*   **`blood_sprite_large`**: Defines the large blood splatter sprite (`data/particles/bloodsplatters/bloodsplatter_green_$[1-3].xml`).
*   **`damage_multipliers`**:
    *   `radioactive`: Set to "0.0", indicating no resistance or vulnerability to radioactive damage.

### SpriteComponent

Defines the visual appearance of the Barfer.

*   **`image_file`**: The sprite image is located at `data/enemies_gfx/barfer.xml`.

### PathFindingComponent

Enables pathfinding capabilities for the entity.

*   **`can_jump`**: Set to "1", allowing the Barfer to jump.

### PathFindingGridMarkerComponent

Marks the entity's presence on the pathfinding grid.

*   **`marker_work_flag`**: Set to "16", indicating a specific flag for pathfinding.

### GenomeDataComponent

Provides genetic information, influencing its role in the ecosystem.

*   **`herd_id`**: Identifies the Barfer's herd as "mage".
*   **`food_chain_rank`**: Assigned a rank of "6" in the food chain.
*   **`is_predator`**: Set to "1", classifying it as a predator.

### CharacterPlatformingComponent

Handles the Barfer's movement mechanics, including jumping and running.

*   **`jump_velocity_y`**: The vertical velocity applied when jumping (-12 units).
*   **`run_velocity`**: The horizontal movement speed (18 units).

### CameraBoundComponent

Manages the entity's behavior relative to the camera's view.

*   **`max_count`**: Maximum number of entities of this type that can be active (30).
*   **`distance`**: The distance from the camera within which the entity is considered active (160000 units).

### HitboxComponent

Defines the physical collision boundaries of the Barfer.

*   **`aabb_min_x` / `aabb_max_x`**: Horizontal bounds of the hitbox (-4.5 to 4.5).
*   **`aabb_min_y` / `aabb_max_y`**: Vertical bounds of the hitbox (-10 to 3).

### CharacterDataComponent

Contains general character data, including collision properties and mass.

*   **`collision_aabb_min_x` / `collision_aabb_max_x`**: Horizontal bounds for collision detection (-4.0 to 3.5).
*   **`collision_aabb_min_y` / `collision_aabb_max_y`**: Vertical bounds for collision detection (-12 to 3).
*   **`mass`**: The mass of the Barfer (1.4).

## Audio Components

These components manage the sound effects associated with the Barfer.

### AudioLoopComponent

Handles looping sound effects, such as movement sounds.

*   **`file`**: The audio bank file (`data/audio/Desktop/animals.bank`).
*   **`event_name`**: The specific audio event for the movement loop ("animals/wizard/movement_loop").
*   **`set_speed_parameter`**: Set to "1", allowing the sound's speed to be adjusted based on movement.
*   **`auto_play`**: Set to "1", meaning the sound plays automatically when the entity is active.

### AudioComponent

Manages general audio events for the entity.

*   **`file`**: The audio bank file (`data/audio/Desktop/animals.bank`).
*   **`event_root`**: The root event name for the Barfer's sounds ("animals/wizard").

## Other Components

### ItemPickUpperComponent

This component allows the entity to pick up items.

*   **`is_in_npc`**: Set to "1", indicating it functions as an NPC for item pickup purposes.