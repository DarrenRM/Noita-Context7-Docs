---
title: Greed Ghost Entity
category: entities
---

---

# Greed Ghost Entity

This document details the `greed_ghost.xml` entity, representing the Greed Ghost enemy in Noita.

## Core Attributes

| Attribute | Description |
|---|---|
| `name` | `$animal_greed_ghost` - Internal name for the entity. |
| `tags` | `enemy,teleportable_NOT,polymorphable_NOT,greed_curse_ghost,glue_NOT` - Defines its behavior and interactions. Notably, it cannot be teleported or polymorphed, and is immune to glue. |

## Components

### ItemChestComponent

This component indicates the Greed Ghost can drop loot.

| Attribute | Description |
|---|---|
| `level` | `4` - Loot drop quality level. |
| `enemy_drop` | `1` - Probability of dropping loot. |

### SpriteComponent

Defines the visual appearance of the Greed Ghost.

| Attribute | Description |
|---|---|
| `image_file` | `data/enemies_gfx/greed_ghost.xml` - Path to the sprite's graphical data. |
| `emissive` | `1` - The sprite emits light. |
| `additive` | `1` - The sprite uses additive blending for its rendering. |
| `z_index` | `0.9` - Controls rendering order. |

### AnimalAIComponent

Governs the creature's artificial intelligence and behavior.

| Attribute | Description |
|---|---|
| `preferred_job` | `JobDefault` - The AI's default task. |
| `creature_detection_range_x`, `creature_detection_range_y` | `300` - Range at which it detects other creatures. |
| `attack_melee_enabled` | `1` - The ghost can perform melee attacks. |
| `food_material` | `blood` - The material it consumes for sustenance. |
| `needs_food` | `1` - The creature requires food to survive. |
| `sense_creatures` | `1` - The creature can sense other creatures. |
| `can_fly` | `1` - The creature is capable of flight. |
| `aggressiveness_min`, `aggressiveness_max` | `1`, `100` - Defines its aggression levels. |

### PathFindingComponent

Handles pathfinding and movement capabilities.

| Attribute | Description |
|---|---|
| `can_dive`, `can_fly`, `can_swim_on_surface` | `1` - Indicates it can dive, fly, and swim on the surface. |
| `can_walk` | `0` - It cannot walk. |
| `cost_of_flying` | `500` - The cost associated with flying in pathfinding calculations. |
| `jump_speed` | `200` - The speed at which it jumps. |

### DamageNearbyEntitiesComponent

Allows the entity to damage entities within a certain radius.

| Attribute | Description |
|---|---|
| `radius` | `16` - The area of effect for damage. |
| `time_between_damaging` | `3` - Delay between damage applications. |
| `target_tag` | `player_unit` - The entity targets the player. |
| `damage_description` | `$greed_curse_damage` - The name of the damage effect. |
| `damage_type` | `DAMAGE_CURSE` - The type of damage dealt. |

### PhysicsAIComponent

Manages the physics-based AI and forces applied to the entity.

| Attribute | Description |
|---|---|
| `target_vec_max_len` | `15.0` - Maximum length of the target vector. |
| `force_coeff` | `14.0` - Coefficient for applying force. |
| `torque_coeff` | `50` - Coefficient for applying torque. |

### PhysicsBodyComponent

Defines the physical properties of the entity's body.

| Attribute | Description |
|---|---|
| `angular_damping` | `0.02` - Reduces rotational velocity over time. |
| `fixed_rotation` | `1` - Prevents the body from rotating. |
| `is_static` | `0` - The body is not static and can be moved. |

### GenomeDataComponent

Contains genetic information, influencing herd behavior and predator status.

| Attribute | Description |
|---|---|
| `herd_id` | `-1` (general), `curse` (specific) - Identifies its herd and curse affiliation. |
| `food_chain_rank` | `10` - Its position in the food chain. |
| `is_predator` | `1` - It is a predator. |