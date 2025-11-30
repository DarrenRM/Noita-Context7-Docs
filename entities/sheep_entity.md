---
title: Sheep Entity
category: entities
---

# Sheep Entity

This document details the `sheep.xml` entity file, which defines the behavior and appearance of sheep in Noita.

## Key Attributes

The sheep entity is built upon `base_helpless_animal.xml` and includes several components that define its AI, physical properties, and visual representation.

### Base Entity Components

*   **`AnimalAIComponent`**:
    *   `preferred_job`: Set to "Escaping", indicating the sheep's primary AI behavior.
    *   `food_material`: "grass", specifying what the sheep consumes.
    *   `needs_food`: "1", meaning the sheep requires food to survive.
    *   `attack_melee_enabled`, `attack_ranged_enabled`: Both set to "0", indicating the sheep cannot attack.

*   **`DamageModelComponent`**:
    *   `hp`: "0.1", defining the sheep's very low health.
    *   `ragdoll_filenames_file`: Points to the sheep's ragdoll configuration.
    *   `materials_create_messages`: "grass", meaning grass material can trigger messages related to the sheep.

*   **`SpriteComponent`**:
    *   `image_file`: "data/enemies_gfx/sheep.xml", specifies the graphical asset for the sheep.
    *   `offset_x`, `offset_y`: Adjust the sprite's position.

*   **`GenomeDataComponent`**:
    *   `herd_id`: "helpless", categorizes the sheep within the game's ecosystem.
    *   `food_chain_rank`: "20", indicating its position in the food chain.
    *   `is_predator`: "0", confirming it is prey.

*   **`CharacterPlatformingComponent`**:
    *   `run_velocity`: "10", defines the sheep's movement speed.
    *   `jump_velocity_y`: "0", indicating no jumping capability.

*   **`HitboxComponent`**:
    *   `aabb_max_x`, `aabb_max_y`, `aabb_min_x`, `aabb_min_y`: Define the bounding box for the sheep's hitbox.

*   **`CharacterDataComponent`**:
    *   `mass`: "1.4", sets the physical mass of the sheep.
    *   `collision_aabb_min_x`, `collision_aabb_max_x`, `collision_aabb_min_y`, `collision_aabb_max_y`: Define the collision area.

*   **`PathFindingComponent`**:
    *   `can_jump`, `jump_speed`, `initial_jump_max_distance_x`, `initial_jump_max_distance_y`: All set to "0", reinforcing the lack of jumping.

### Audio Component

*   **`AudioComponent`**:
    *   `file`: "data/audio/Desktop/animals.bank", specifies the audio bank.
    *   `event_root`: "animals/sheep", defines the root event for sheep sounds.

## Summary

The sheep entity is designed as a passive, prey animal with a focus on escaping threats. Its low health and lack of offensive capabilities make it a vulnerable creature in the Noita world. The entity utilizes standard Noita components for AI, physics, visuals, and audio, with specific configurations for its docile nature and dietary needs.