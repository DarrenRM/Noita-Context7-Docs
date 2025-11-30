---
title: Sheep Fly Entity
category: entities
---

# Sheep Fly Entity

This document describes the `sheep_fly.xml` entity, a passive flying creature in Noita.

## Core Components

The `sheep_fly` entity is built upon several core components that define its behavior, appearance, and physical properties.

### Base Entity

The entity inherits its fundamental structure from `data/entities/base_helpless_animal.xml`.

### AnimalAIComponent

This component governs the AI and behavior of the sheep fly.

*   **`preferred_job`**: Set to `"Escaping"`, indicating its primary AI directive is to flee from threats.
*   **`can_fly`**: Set to `"1"`, confirming its ability to fly.
*   **`food_material`**: `"grass"`, suggesting it might interact with or consume grass in some way, though `needs_food` is disabled.
*   **`needs_food`**: Set to `"0"`, meaning it does not require sustenance to survive.
*   **Attack Components**: All attack-related components (`attack_melee_enabled`, `attack_ranged_entity_file`, `attack_ranged_enabled`) are disabled, reinforcing its passive nature.

### DamageModelComponent

Defines how the entity takes damage and its resulting physical state.

*   **`hp`**: Set to `"0.2"`, indicating it is very fragile and easily defeated.
*   **`ragdoll_filenames_file`**: `"data/ragdolls/sheep_fly/filenames.txt"`, specifying the files used for its ragdoll physics upon death.
*   **`materials_create_messages`**: `"1"`, enabling the creation of messages when materials interact with it.
*   **`materials_that_create_messages`**: `"grass"`, indicating that grass is a material that can trigger these messages.

### SpriteComponent

Determines the visual representation of the sheep fly.

*   **`image_file`**: `"data/enemies_gfx/sheep_fly.xml"`, points to the graphical definition of the sheep fly.
*   **`offset_x`**: `"10"`
*   **`offset_y`**: `"12"`

### SpriteAnimatorComponent

Handles sprite animations.

*   **`rotate_to_surface_normal`**: `"0"`, meaning the sprite does not automatically orient itself to the surface normal.

### PathFindingGridMarkerComponent

Used for pathfinding calculations.

*   **`marker_work_flag`**: `"24"`, a flag used internally for pathfinding.

### GenomeDataComponent

Provides genetic information for the entity.

*   **`herd_id`**: `"helpless"`, categorizes it within a group of helpless creatures.
*   **`food_chain_rank`**: `"20"`, indicating its position in the food chain.
*   **`is_predator`**: `"0"`, confirming it is not a predator.

### CharacterPlatformingComponent

Defines movement characteristics.

*   **`run_velocity`**: `"10"`, sets its horizontal movement speed.
*   **`jump_velocity_y`**: `"0"`, it cannot jump vertically.

### HitboxComponent

Defines the collision area for interactions.

*   **`aabb_max_x`**: `"6"`
*   **`aabb_max_y`**: `"4"`
*   **`aabb_min_x`**: `"-6"`
*   **`aabb_min_y`**: `"-7"`

### CharacterDataComponent

General character data, including collision and mass.

*   **`collision_aabb_min_x`**: `"-3.0"`
*   **`collision_aabb_max_x`**: `"3.0"`
*   **`collision_aabb_min_y`**: `"-6"`
*   **`collision_aabb_max_y`**: `"2"`
*   **`buoyancy_check_offset_y`**: `"-3"`
*   **`mass`**: `"1.4"`

### PathFindingComponent

Enables and configures pathfinding capabilities.

*   **`can_fly`**: `"1"`, explicitly allows flying.
*   **`can_walk`**: `"0"`, it cannot walk.
*   **`can_jump`**: `"0"`, it cannot jump.

## Audio Components

These components manage the sound effects associated with the sheep fly.

### AudioComponent

*   **`file`**: `"data/audio/Desktop/animals.bank"`
*   **`event_root`**: `"animals/sheep"`

### AudioLoopComponent

Handles looping sound effects, likely for movement.

*   **`file`**: `"data/audio/Desktop/animals.bank"`
*   **`event_name`**: `"animals/wing_flap_insect/movement_loop"`
*   **`set_speed_parameter`**: `"1"`
*   **`set_speed_parameter_only_based_on_y_movement`**: `"1"`
*   **`auto_play`**: `"1"`