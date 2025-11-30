---
title: Frog Entity
category: entities
---

# Frog Entity

This document details the configuration for the Frog entity in Noita, primarily focusing on its AI, physical properties, and visual representation.

## Core Components

The Frog entity is built upon a `Base` entity, inheriting common functionalities for enemies and creatures.

### `Base` Entity Inheritance

The frog inherits from `data/entities/base_enemy_basic.xml`.

### `AnimalAIComponent`

This component governs the frog's behavior and intelligence.

*   **`_enabled`**: `1` - Enables AI functionality.
*   **`preferred_job`**: `JobDefault` - The default job assigned to the frog.
*   **`escape_if_damaged_probability`**: `35` - The percentage chance the frog will attempt to flee when damaged.
*   **`attack_dash_enabled`**: `1` - Enables a dash attack.
*   **`attack_dash_damage`**: `0.4` - The damage dealt by the dash attack.
*   **`creature_detection_range_x` / `creature_detection_range_y`**: `250` - The range (in pixels) at which the frog detects other creatures.
*   **`food_material`**: `meat` - The material the frog consumes for sustenance.
*   **`needs_food`**: `1` - Indicates the frog requires food to survive.
*   **`sense_creatures`**: `1` - Enables the frog's ability to sense nearby creatures.
*   **`defecates_and_pees`**: `1` - The frog produces waste.

### `DamageModelComponent`

Manages the frog's health and how it reacts to damage.

*   **`hp`**: `0.3` - The frog's health points.
*   **`materials_create_messages`**: `1` - When damaged, it can create messages (e.g., for drops).
*   **`ragdoll_material`**: `meat_frog` - The material used for the frog's ragdoll upon death.
*   **`ragdoll_filenames_file`**: `data/ragdolls/frog/filenames.txt` - Specifies the files used for the frog's ragdoll.

### `SpriteComponent`

Defines the visual appearance of the frog.

*   **`image_file`**: `data/enemies_gfx/frog.xml` - Points to the sprite definition file.
*   **`rect_animation`**: `stand` - The default animation state is "stand".
*   **`offset_x` / `offset_y`**: `0` - No offset applied to the sprite.

### `PathFindingComponent`

Controls the frog's movement and navigation.

*   **`distance_to_reach_node_x` / `distance_to_reach_node_y`**: `20` - The tolerance for reaching a pathfinding node.
*   **`can_swim_on_surface`**: `1` - The frog can swim on the water's surface.
*   **`can_dive`**: `1` - The frog can dive underwater.
*   **`frames_to_get_stuck`**: `20` - Number of frames before the frog is considered stuck.
*   **`initial_jump_lob`**: `2` - Controls the arc of its initial jump.
*   **`can_walk`**: `0` - The frog cannot walk.
*   **`can_jump`**: `1` - The frog can jump.

### `GenomeDataComponent`

Provides genetic information for AI and ecosystem interactions.

*   **`herd_id`**: `slimes` - Identifies the frog as part of the "slimes" herd.
*   **`food_chain_rank`**: `10` - Its position in the food chain.
*   **`is_predator`**: `1` - The frog is a predator.

### `CharacterDataComponent`

Defines the physical collision and mass properties.

*   **`collision_aabb_min_x` / `collision_aabb_max_x`**: `-2.0` / `2.0` - Defines the horizontal collision bounds.
*   **`collision_aabb_min_y` / `collision_aabb_max_y`**: `-4` / `3` - Defines the vertical collision bounds.
*   **`buoyancy_check_offset_y`**: `-4` - The vertical offset for buoyancy checks.
*   **`mass`**: `0.6` - The mass of the frog.

### `CharacterPlatformingComponent`

Governs platforming-specific movement parameters.

*   **`pixel_gravity`**: `600` - The gravity applied to the frog.
*   **`jump_velocity_y`**: `-12` - The initial upward velocity when jumping.
*   **`run_velocity`**: `0` - The frog has no inherent running speed.

### `HitboxComponent`

Defines the active hitbox for interactions.

*   **`aabb_min_x` / `aabb_max_x`**: `-1.5` / `1.5` - Horizontal bounds of the hitbox.
*   **`aabb_min_y` / `aabb_max_y`**: `-2.5` / `3` - Vertical bounds of the hitbox.
*   **`is_enemy`**: `1` - This hitbox belongs to an enemy.

### `CameraBoundComponent`

Manages how the camera behaves relative to the entity.

*   **`max_count`**: `20` - Maximum number of this entity that can be active within camera bounds.
*   **`distance`**: `160000` - The radius (squared) within which the entity affects the camera.

### `AudioComponent`

Handles sound effects associated with the frog.

*   **`file`**: `data/audio/Desktop/animals.bank` - The audio bank containing frog sounds.
*   **`event_root`**: `animals/frog` - The root event name for frog-related audio.