---
title: Slime Shooter Boss Limbs
category: entities
---

# Slime Shooter Boss Limbs

This document details the configuration for the "Slime Shooter Boss Limbs" entity in Noita, primarily focusing on its AI, combat, and physical attributes.

## Core Entity Configuration

The `slimeshooter_boss_limbs.xml` file defines a specific type of enemy entity, likely a component of a larger boss. It inherits core functionalities from `base_enemy_flying.xml`.

### Key Components and Attributes

*   **`name`**: `$animal_slimeshooter_boss_limbs` - The internal identifier for this entity.
*   **`tags`**: `slimeshooter_boss_limbs` - Used for entity identification and interaction.

### `Base` Component (`data/entities/base_enemy_flying.xml`)

This is the primary component defining the entity's behavior and properties.

#### `AnimalAIComponent`

Manages the entity's artificial intelligence and combat actions.

*   **`attack_ranged_entity_file`**: `data/entities/animals/boss_limbs/slime_boss_limbs.xml` - Specifies the entity to be spawned for ranged attacks.
*   **`attack_ranged_enabled`**: `1` - Enables ranged attacks.
*   **`attack_dash_enabled`**: `0` - Disables dashing behavior.
*   **`attack_ranged_action_frame`**: `2` - The frame at which the ranged attack action is initiated.
*   **`attack_ranged_frames_between`**: `40` - The number of frames to wait between ranged attacks.
*   **`attack_ranged_max_distance`**: `120` - The maximum distance from which ranged attacks can be performed.
*   **`can_fly`**: `1` - Allows the entity to fly.

#### `DamageModelComponent`

Defines the entity's health and how it reacts to damage.

*   **`hp`**: `5.7` - The entity's hit points.
*   **`ragdoll_filenames_file`**: `data/ragdolls/slimeshooter/filenames_boss_limbs.txt` - Points to the file defining the ragdoll's appearance upon death.
*   **`ragdoll_material`**: `meat_slime_green` - The material used for the ragdoll.
*   **`blood_material`**: `radioactive_liquid_fading` - The material that spills when the entity takes damage.

#### `PathFindingComponent`

Determines how the entity navigates the game world.

*   **`can_fly`**: `1` - Confirms the entity's ability to fly for pathfinding.

#### `SpriteComponent`

Handles the visual representation of the entity.

*   **`image_file`**: `data/entities/animals/boss_limbs/slimeshooter_boss.xml` - The sprite sheet or definition file for the entity's appearance.
*   **`offset_x`**, **`offset_y`**: `0` - The sprite's position relative to the entity's origin.

#### `GenomeDataComponent`

Relates to the entity's genetic properties, often for spawning and herd behavior.

*   **`herd_id`**: `boss_limbs` - Identifies the herd this entity belongs to.

#### `HitboxComponent`

Defines the collision boundaries for the entity.

*   **`aabb_min_x`**, **`aabb_max_x`**: `-4.0`, `4.0` - The bounding box limits on the X-axis.
*   **`aabb_min_y`**, **`aabb_max_y`**: `-11`, `-2` - The bounding box limits on the Y-axis.
*   **`is_enemy`**: `1` - Marks this entity as an enemy.
*   **`is_item`**: `0` - Not an item.
*   **`is_player`**: `0` - Not a player.

#### `CharacterDataComponent`

Provides specific character-related properties.

*   **`climb_over_y`**: `4` - The Y-axis threshold for climbing over obstacles.
*   **`collision_aabb_min_x`**, **`collision_aabb_max_x`**: `-2.0`, `2.0` - Collision box limits on the X-axis.
*   **`collision_aabb_min_y`**, **`collision_aabb_max_y`**: `-10`, `0` - Collision box limits on the Y-axis.

### `LightComponent`

Adds a light source to the entity.

*   **`radius`**: `30` - The radius of the light.
*   **`r`**, **`g`**, **`b`**: `99`, `205`, `139` - The RGB color values of the light (a greenish hue).
*   **`offset_y`**: `-9` - The vertical offset of the light source.

### `MaterialInventoryComponent`

Manages the materials contained within the entity, particularly those that leak.

*   **`drop_as_item`**: `0` - Materials do not drop as items.
*   **`leak_on_damage_percent`**: `0.999` - The entity will leak its contained materials when it reaches 99.9% damage.
*   **`count_per_material_type`**:
    *   **`Material material="radioactive_liquid_fading" count="800"`**: The entity contains 800 units of `radioactive_liquid_fading`.

### Attached Entities (Limbs/Tentacles)

The entity spawns additional child entities, likely representing its limbs or tentacles, which inherit transformations.

*   **Slime Tentacle Bright 02**: Attached with an offset of `(0, -4)`.
*   **Slime Tentacle Bright 01**: Attached with an offset of `(-3, -4)`.
*   **Slime Tentacle Thin 01**: Attached with an offset of `(3, -4)`.