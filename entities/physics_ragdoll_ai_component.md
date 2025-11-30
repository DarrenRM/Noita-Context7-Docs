---
title: Physics Ragdoll AI Component
category: entities
---

# Physics Ragdoll AI Component

This entity defines a basic flying creature with physics-based AI, primarily for ragdoll behavior and simple movement. It's designed to be a prey animal.

## Key Components and Attributes

### PhysicsAIComponent
Controls the physics-driven movement and behavior of the entity.

*   **`target_vec_max_len`**: Maximum length of the target vector for movement. (14.0)
*   **`force_coeff`**: Coefficient for applying force. (17.0)
*   **`force_max`**: Maximum force that can be applied. (90)
*   **`torque_coeff`**: Coefficient for applying torque. (30)
*   **`torque_max`**: Maximum torque that can be applied. (30.0)
*   **`damage_deactivation_probability`**: Chance (in %) for the AI to deactivate upon taking damage. (20)
*   **`damage_deactivation_time_min`**: Minimum duration (in frames) the AI stays deactivated after taking damage. (30)
*   **`damage_deactivation_time_max`**: Maximum duration (in frames) the AI stays deactivated after taking damage. (60)

### LightComponent
Adds a light source to the entity.

*   **`radius`**: The radius of the light. (200)
*   **`r`, `g`, `b`**: RGB color values for the light. (135, 10, 180)

### Base (Inherited from `base_enemy_flying.xml`)

This section inherits and configures common enemy properties.

#### AnimalAIComponent
Manages creature-like AI behaviors.

*   **`creature_detection_range_x`, `creature_detection_range_y`**: Range at which the creature detects other creatures. (300, 300)
*   **`attack_ranged_enabled`**: Whether ranged attacks are enabled. (0 - disabled)
*   **`can_fly`**: Indicates if the creature can fly. (1 - enabled)
*   **`needs_food`**: Whether the creature requires food. (0 - disabled)
*   **`eye_offset_y`**: Vertical offset for the creature's eyes. (-5)

#### DamageModelComponent
Defines health and damage-related properties.

*   **`hp`**: Hit points of the entity. (6)
*   **`ragdoll_material`**: Material used for the ragdoll. ("meat")
*   **`blood_material`**: Material for blood effects. ("plasma_fading_pink")
*   **`fire_probability_of_ignition`**: Chance of igniting from fire. (0)

##### damage_multipliers
Defines multipliers for different damage types.

| Type       | Multiplier |
| :--------- | :--------- |
| `melee`    | 0.3        |
| `projectile` | 0.3        |
| `explosion`| 1.0        |
| `electricity`| 0.1        |
| `fire`     | 0          |

#### SpriteComponent
Handles visual representation.

*   **`image_file`**: Path to the sprite image. (Empty, likely uses default from base)

#### PathFindingComponent
Enables pathfinding capabilities.

*   **`distance_to_reach_node_x`, `distance_to_reach_node_y`**: Distance thresholds for reaching pathfinding nodes. (20, 20)
*   **`frames_to_get_stuck`**: Frames before the entity is considered stuck. (120)
*   **`can_fly`**: Whether pathfinding supports flying. (1 - enabled)

#### GenomeDataComponent
Defines genetic and ecological properties.

*   **`herd_id`**: Identifier for the creature's herd. ("helpless")
*   **`food_chain_rank`**: Rank in the food chain. (15)
*   **`is_predator`**: Whether the creature is a predator. (0 - false)

#### CharacterPlatformingComponent
Manages platforming and movement parameters.

*   **`run_velocity`**: Horizontal movement speed. (24)

#### HitboxComponent
Defines the collision hitbox.

*   **`aabb_max_x`, `aabb_max_y`**: Maximum extents of the Axis-Aligned Bounding Box. (5, 0)
*   **`aabb_min_x`, `aabb_min_y`**: Minimum extents of the Axis-Aligned Bounding Box. (-5, -12)

#### CharacterDataComponent
Core character data.

*   **`collision_aabb_min_x`, `collision_aabb_max_x`**: Collision box extents. (-4, 4)
*   **`collision_aabb_min_y`, `collision_aabb_max_y`**: Collision box extents. (-6, 2)
*   **`mass`**: Mass of the character. (1.9)

### ItemPickUpperComponent
Allows the entity to pick up items.

*   **`is_in_npc`**: Indicates if this component is used by an NPC. (1 - true)

### VariableStorageComponent
Stores entity-specific variables.

*   **`_tags`**: Tags associated with the variable storage. ("no_gold_drop" - implies it won't drop gold)