---
title: Slimeshooter Boss Limbs
category: entities
---

# Slimeshooter Boss Limbs

This entity represents the limbs of the Slimeshooter boss in Noita. It's designed to be a flying, ranged attacker with a focus on slime-based mechanics.

## Key Components and Attributes

### Base Entity

*   **`Base file="data/entities/base_enemy_flying.xml"`**: Inherits core functionality from the flying enemy base.

### AI Component (`AnimalAIComponent`)

*   **`attack_ranged_entity_file="data/entities/animals/boss_limbs/slime_boss_limbs.xml"`**: Specifies the entity to be spawned when performing a ranged attack.
*   **`attack_ranged_enabled="1"`**: Enables the ranged attack capability.
*   **`attack_dash_enabled="0"`**: Disables dash attacks.
*   **`attack_ranged_action_frame="2"`**: The frame at which the ranged attack action is triggered.
*   **`attack_ranged_frames_between="40"`**: The number of frames to wait between ranged attacks.
*   **`attack_ranged_max_distance="120"`**: The maximum distance at which the boss can perform a ranged attack.
*   **`can_fly="1"`**: Allows the entity to fly.

### Damage Component (`DamageModelComponent`)

*   **`hp="0.7"`**: The health of the boss limb.
*   **`ragdoll_filenames_file="data/ragdolls/slimeshooter/filenames_boss_limbs.txt"`**: Specifies the files for the ragdoll effect upon death.
*   **`ragdoll_material="meat_slime_green"`**: The material used for the ragdoll.
*   **`blood_material="radioactive_liquid_fading"`**: The material that leaks when damaged.

### Pathfinding Component (`PathFindingComponent`)

*   **`can_fly="1"`**: Enables flight for pathfinding.

### Sprite Component (`SpriteComponent`)

*   **`image_file="data/entities/animals/boss_limbs/slimeshooter_boss.xml"`**: The sprite file used for the boss limb.

### Hitbox Component (`HitboxComponent`)

*   **`aabb_min_x="-4.0"`, `aabb_max_x="4.0"`, `aabb_min_y="-11"`, `aabb_max_y="-2"`**: Defines the bounding box for collision detection.
*   **`is_enemy="1"`**: Marks this entity as an enemy.

### Character Data Component (`CharacterDataComponent`)

*   **`climb_over_y="4"`**: The vertical distance the character can climb over.
*   **`collision_aabb_min_x="-2.0"`, `collision_aabb_max_x="2.0"`, `collision_aabb_min_y="-10"`, `collision_aabb_max_y="0"`**: Defines the collision bounding box for the character.

### Light Component (`LightComponent`)

*   **`radius="30"`**: The radius of the light emitted.
*   **`r="99"`, `g="205"`, `b="139"`**: The RGB color of the light (a greenish hue).
*   **`offset_y="-9"`**: The vertical offset of the light source.

### Material Inventory Component (`MaterialInventoryComponent`)

*   **`drop_as_item="0"`**: Prevents the material from being dropped as an item.
*   **`leak_on_damage_percent="0.999"`**: The percentage of damage at which the material starts leaking.
*   **`Material material="radioactive_liquid_fading" count="800"`**: Specifies that the entity contains 800 units of "radioactive_liquid_fading" material.

### Attached Entities

This entity spawns several "slime tentacle" entities, likely for visual or functional purposes.

*   **`slime_tentacle_bright_02.xml`**: Attached with a vertical offset of -4.
*   **`slime_tentacle_bright_01.xml`**: Attached with a horizontal offset of -3 and vertical offset of -4.
*   **`slime_tentacle_thin_01.xml`**: Attached with a horizontal offset of 3 and vertical offset of -4.