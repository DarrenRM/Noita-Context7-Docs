---
title: Base Humanoid Entity
category: entities
---

---

# Base Humanoid Entity

This document details the core components and attributes of the `base_humanoid.xml` entity, serving as a foundational template for humanoid characters in Noita.

## Core Entity Tags

These tags define the fundamental nature and interactions of the humanoid entity.

*   `mortal`: The entity can be killed.
*   `human`: Identifies the entity as a human.
*   `hittable`: The entity can be targeted and hit by attacks.
*   `homing_target`: Projectiles can home in on this entity.
*   `teleportable_NOT`: The entity cannot be teleported.
*   `destruction_target`: The entity can be destroyed.

## Key Components

### AnimalAIComponent

Manages the AI behavior of the humanoid, including movement, detection, and combat.

*   **`creature_detection_range_x`**: 180 - Horizontal range for detecting other creatures.
*   **`creature_detection_range_y`**: 40 - Vertical range for detecting other creatures.
*   **`attack_melee_max_distance`**: 10 - Maximum distance for melee attacks.
*   **`attack_melee_damage_min`**: 0.2 - Minimum damage dealt by melee attacks.
*   **`attack_melee_damage_max`**: 0.4 - Maximum damage dealt by melee attacks.
*   **`attack_ranged_enabled`**: 0 - Ranged attacks are disabled by default.
*   **`attack_melee_enabled`**: 1 - Melee attacks are enabled by default.
*   **`can_fly`**: 1 - The entity can fly.
*   **`food_material`**: "meat" - The material dropped when eaten.
*   **`food_eating_create_particles`**: 1 - Particles are created when eating.

### PathFindingComponent

Handles pathfinding and movement logic.

*   **`search_depth_max_no_goal`**: 120 - Maximum search depth when no specific goal is set.
*   **`cost_of_flying`**: 1100 - The cost associated with flying movement.
*   **`frames_to_get_stuck`**: 30 - Frames before considering the entity stuck.
*   **`can_fly`**: 0 - Flying is disabled for pathfinding movement (overridden by `AnimalAIComponent`).
*   **`can_jump`**: 0 - Jumping is disabled for pathfinding movement.
*   **`jump_trajectories`**: Defines various jump arcs with `x`, `y`, and `lob` parameters.

### CharacterCollisionComponent

Defines collision properties for the character.

*   **`getting_crushed_threshold`**: 6 - Threshold for damage when being crushed.

### CharacterDataComponent

Contains fundamental character data and physics properties.

*   **`check_collision_max_size_x`**: 4 - Maximum X-axis size for collision checks.
*   **`check_collision_max_size_y`**: 4 - Maximum Y-axis size for collision checks.
*   **`climb_over_y`**: 4 - Vertical distance the character can climb over.
*   **`collision_aabb_min_x`**: -2.0 - Minimum X-axis bounding box for collision.
*   **`collision_aabb_max_x`**: 2.0 - Maximum X-axis bounding box for collision.
*   **`collision_aabb_min_y`**: -3 - Minimum Y-axis bounding box for collision.
*   **`collision_aabb_max_y`**: 3 - Maximum Y-axis bounding box for collision.
*   **`gravity`**: 0 - Gravity is disabled for this entity.
*   **`buoyancy_check_offset_y`**: -6 - Offset for buoyancy checks.

### GenomeDataComponent

Relates to genetic properties and creature hierarchy.

*   **`herd_id`**: "player" - Identifies this as part of the player's herd.
*   **`food_chain_rank`**: 20 - Rank in the food chain.
*   **`is_predator`**: 1 - The entity is a predator.

### CharacterPlatformingComponent

Manages platforming mechanics like running, jumping, and flying.

*   **`jump_velocity_y`**: -125 - Vertical velocity applied when jumping.
*   **`fly_speed_max_up`**: 90 - Maximum upward flying speed.
*   **`fly_speed_max_down`**: 90 - Maximum downward flying speed.
*   **`fly_speed_mult`**: 20 - Multiplier for flying speed.
*   **`pixel_gravity`**: 600 - Gravity applied per pixel.
*   **`run_velocity`**: 28 - Base running speed.
*   **`accel_x`**: 0.15 - Horizontal acceleration.
*   **`velocity_max_x`**: 50 - Maximum horizontal velocity.
*   **`velocity_max_y`**: 350 - Maximum vertical velocity.

### DamageModelComponent

Defines how the entity takes damage and its resistances.

*   **`hp`**: 1 - Hit points of the entity.
*   **`falling_damage_damage_max`**: 1.2 - Maximum damage from falling.
*   **`falling_damage_height_max`**: 250 - Maximum height for falling damage calculation.
*   **`fire_probability_of_ignition`**: 0.5 - Probability of igniting from fire.
*   **`materials_that_damage`**: A list of materials that inflict damage (e.g., "acid", "lava", "poison").
*   **`materials_how_much_damage`**: Corresponding damage values for each material in `materials_that_damage`.
*   **`ragdoll_material`**: "meat" - The material used for the ragdoll.

### SpriteComponent

Controls the visual representation of the entity.

*   **`image_file`**: "data/enemies_gfx/player.xml" - Path to the sprite's image file.
*   **`offset_x`**: 6 - Horizontal offset for the sprite.
*   **`offset_y`**: 13 - Vertical offset for the sprite.
*   **`rect_animation`**: "walk" - The default rectangle animation to play.

### AudioComponent

Manages sound effects for the entity.

*   **`file`**: "data/audio/Desktop/animals.bank" - The audio bank file.
*   **`event_root`**: "animals" or "animals/generic" - The root event for animal sounds.