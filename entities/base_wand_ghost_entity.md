---
title: Base Wand Ghost Entity
category: entities
---

# Base Wand Ghost Entity

This document describes the `base_wand_ghost.xml` entity, which serves as a foundational template for the "Wand Ghost" enemy in Noita. It defines its physical properties, AI behavior, combat capabilities, and visual representation.

## Key Components and Attributes

### PhysicsAIComponent
Controls the entity's movement and response to forces.

*   **`target_vec_max_len`**: Maximum length of the target vector for movement (15.0).
*   **`force_coeff`**: Coefficient for applying force (20.0).
*   **`damage_deactivation_probability`**: Chance (in percent) for the entity to deactivate upon taking damage (80).
*   **`damage_deactivation_time_min`**: Minimum duration (in frames) the entity remains deactivated after taking damage (60).
*   **`damage_deactivation_time_max`**: Maximum duration (in frames) the entity remains deactivated after taking damage (120).

### PhysicsBodyComponent
Defines the physical body properties.

*   **`allow_sleep`**: Whether the body can enter a sleep state (1 - enabled).
*   **`angular_damping`**: Damping applied to angular velocity (0.02).
*   **`linear_damping`**: Damping applied to linear velocity (0).

### PhysicsShapeComponent
Defines the collision shape of the entity.

*   **`is_circle`**: Whether the shape is a circle (1 - true).
*   **`radius_x`**: Radius along the X-axis (5).
*   **`radius_y`**: Radius along the Y-axis (5).
*   **`friction`**: Friction coefficient (0.0).
*   **`restitution`**: Bounciness (0.3).

### Base (Inherited from `base_enemy_flying.xml`)
This entity inherits core functionalities from `base_enemy_flying.xml`.

#### AnimalAIComponent
Governs the creature's AI and behavior.

*   **`preferred_job`**: The AI's preferred task (JobDefault).
*   **`attack_ranged_min_distance`**: Minimum distance for ranged attacks (0).
*   **`attack_ranged_max_distance`**: Maximum distance for ranged attacks (50).
*   **`creature_detection_range_x`**: Detection range on the X-axis (300).
*   **`creature_detection_range_y`**: Detection range on the Y-axis (300).
*   **`attack_ranged_enabled`**: Whether ranged attacks are enabled (1 - true).
*   **`attack_melee_enabled`**: Whether melee attacks are enabled (0 - false).
*   **`can_fly`**: Whether the creature can fly (1 - true).
*   **`attack_ranged_entity_file`**: The entity file used for ranged attacks (`data/entities/projectiles/orb_pink.xml`).
*   **`attack_ranged_frames_between`**: Frames between ranged attacks (10).

#### DamageModelComponent
Manages health and damage interactions.

*   **`hp`**: Hit points of the entity (1.5).
*   **`ragdoll_material`**: Material for the ragdoll effect (crystal).
*   **`blood_material`**: Material for blood effects (plasma_fading).
*   **`fire_probability_of_ignition`**: Probability of igniting from fire (0).
*   **`air_needed`**: Whether air is required for survival (0).

##### damage_multipliers
Defines multipliers for different damage types.

| Type       | Multiplier |
| :--------- | :--------- |
| melee      | 1.0        |
| projectile | 1.0        |
| explosion  | 1.0        |
| electricity| 0.1        |
| fire       | 0          |

#### SpriteComponent
Defines the visual appearance.

*   **`image_file`**: The sprite image file (empty, likely uses a default or inherited sprite).
*   **`offset_x`**: X-axis offset for the sprite (0).
*   **`offset_y`**: Y-axis offset for the sprite (0).

#### PathFindingComponent
Handles pathfinding and movement logic.

*   **`distance_to_reach_node_x`**: Distance to reach a node on the X-axis (20).
*   **`distance_to_reach_node_y`**: Distance to reach a node on the Y-axis (20).
*   **`frames_to_get_stuck`**: Frames before considering the entity stuck (120).
*   **`can_fly`**: Whether the entity can fly during pathfinding (1 - true).

#### GenomeDataComponent
Information related to the entity's genetic makeup and role in the ecosystem.

*   **`herd_id`**: Identifier for the entity's herd (ghost).
*   **`food_chain_rank`**: Position in the food chain (7).
*   **`is_predator`**: Whether the entity is a predator (1 - true).

#### CharacterPlatformingComponent
Defines platforming-related movement parameters.

*   **`jump_velocity_y`**: Vertical jump velocity (0).
*   **`run_velocity`**: Running speed (24).

#### HitboxComponent
Defines the entity's hitbox for interactions.

*   **`aabb_max_x`**: Maximum X-coordinate of the Axis-Aligned Bounding Box (5).
*   **`aabb_max_y`**: Maximum Y-coordinate of the Axis-Aligned Bounding Box (0).
*   **`aabb_min_x`**: Minimum X-coordinate of the Axis-Aligned Bounding Box (-5).
*   **`aabb_min_y`**: Minimum Y-coordinate of the Axis-Aligned Bounding Box (-12).

#### CharacterDataComponent
General character data.

*   **`collision_aabb_min_x`**: Minimum X-coordinate for collision ( -3).
*   **`collision_aabb_max_x`**: Maximum X-coordinate for collision (3).
*   **`collision_aabb_min_y`**: Minimum Y-coordinate for collision (-3).
*   **`collision_aabb_max_y`**: Maximum Y-coordinate for collision (3).

### ItemPickUpperComponent
Component related to picking up items.

*   **`is_immune_to_kicks`**: Whether the entity is immune to kicks (1 - true).
*   **`is_in_npc`**: Whether the entity is considered part of an NPC (1 - true).