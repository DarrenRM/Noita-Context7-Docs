---
title: Duck Entity
category: entities
---

# Duck Entity

This document details the attributes of the Duck entity in Noita, useful for AI-assisted modding.

## Core Attributes

The Duck is a simple, non-aggressive creature with basic AI behaviors.

### Entity Tags

*   `mortal`: The entity can be killed.
*   `prey`: The entity is a potential target for predators.

### Base Entity

The Duck inherits its core functionality from `data/entities/base_helpless_animal.xml`.

## Key Components

### AnimalAIComponent

This component governs the Duck's artificial intelligence and behavior.

*   `preferred_job`: `JobDefault` - Indicates a default job or state.
*   `attack_melee_enabled`: `0` - Cannot perform melee attacks.
*   `attack_ranged_enabled`: `0` - Cannot perform ranged attacks.
*   `sense_creatures`: `1` - Can detect other creatures.
*   `creature_detection_range_x`: `128` - Horizontal range for creature detection.
*   `creature_detection_range_y`: `160` - Vertical range for creature detection.
*   `can_fly`: `0` - Cannot fly.

### DamageModelComponent

Defines the damage and health properties of the Duck.

*   `ragdoll_filenames_file`: `data/ragdolls/duck/filenames.txt` - Specifies the ragdoll files used upon death.
*   `fire_probability_of_ignition`: `0.05` - Low chance of igniting from fire.
*   `hp`: `0.1` - Very low health, making it easily defeated.

### SpriteComponent

Controls the visual representation of the Duck.

*   `image_file`: `data/enemies_gfx/duck.xml` - Points to the sprite definition for the duck.
*   `rect_animation`: `stand` - The default animation state is "stand".

### PathFindingComponent

Manages the Duck's movement and pathfinding capabilities.

*   `distance_to_reach_node_x`: `20` - Horizontal distance considered "reached" for pathfinding nodes.
*   `distance_to_reach_node_y`: `20` - Vertical distance considered "reached" for pathfinding nodes.
*   `frames_to_get_stuck`: `20` - Number of frames before the AI considers itself stuck.
*   `can_jump`: `1` - The Duck can jump.

### GenomeDataComponent

Provides genetic information relevant to AI and ecosystem simulation.

*   `herd_id`: `helpless` - Identifies the Duck as part of a "helpless" group.
*   `food_chain_rank`: `20` - A rank indicating its position in the food chain.
*   `is_predator`: `0` - The Duck is not a predator.

### CharacterDataComponent

Defines physical properties and collision boundaries.

*   `collision_aabb_min_x`: `-2.6`
*   `collision_aabb_max_x`: `2.6`
*   `collision_aabb_min_y`: `-6`
*   `collision_aabb_max_y`: `3` - Defines the bounding box for collision detection.
*   `mass`: `0.3` - The Duck's mass.

### CharacterPlatformingComponent

Governs movement mechanics like running and jumping.

*   `jump_velocity_y`: `-12` - The vertical velocity applied when jumping.
*   `run_velocity`: `30` - The base running speed.
*   `velocity_max_y`: `60` - The maximum vertical velocity.
*   `run_animation_velocity_switching_enabled`: `1` - Animation can switch based on velocity.
*   `run_animation_velocity_switching_threshold`: `20` - The velocity threshold for animation switching.

### HitboxComponent

Defines the entity's hitbox for interactions.

*   `aabb_min_x`: `-4.5`
*   `aabb_max_x`: `4.5`
*   `aabb_min_y`: `-5.5`
*   `aabb_max_y`: `3` - Defines the hitbox dimensions.