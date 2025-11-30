---
title: Tentacler Enemy Entity
category: entities
---

# Tentacler Enemy Entity

This document details the `tentacler.xml` entity, defining the behavior and attributes of the Tentacler enemy in Noita.

## Core Attributes

The Tentacler is a flying enemy with a focus on ranged attacks and a moderate health pool. It exhibits aggressive behavior when it detects creatures.

### `Base` Entity Attributes

The Tentacler inherits from `base_enemy_flying.xml`, gaining core flying enemy functionalities.

*   **`AnimalAIComponent`**:
    *   `preferred_job`: `JobDefault` (Standard AI behavior)
    *   `escape_if_damaged_probability`: `100` (Will always attempt to flee when damaged)
    *   `attack_melee_damage_min`/`max`: `0.4`/`0.7` (Low melee damage potential, though melee attacks are disabled by default)
    *   `creature_detection_range_x`/`y`: `400`/`400` (Large detection radius)
    *   `creature_detection_angular_range_deg`: `60` (Detects creatures within a 60-degree arc)
    *   `sense_creatures`: `1` (Actively senses nearby creatures)
    *   `can_fly`: `1` (Capable of flight)
    *   `aggressiveness_min`/`max`: `1`/`80` (Varies in aggressiveness)

*   **`DamageModelComponent`**:
    *   `hp`: `5` (Relatively low health)
    *   `ragdoll_material`: `meat_slime`
    *   `blood_material`: `blood_fungi`
    *   `blood_multiplier`: `0.3`
    *   `damage_multipliers`:
        *   `projectile`: `0.7` (Takes 70% damage from projectiles)
        *   `freeze`: `0.4` (Takes 40% damage from freeze effects)

*   **`SpriteComponent`**:
    *   `image_file`: `data/enemies_gfx/tentacler.xml` (Specifies the visual assets)

*   **`PathFindingComponent`**:
    *   `can_fly`: `1` (Crucial for its aerial movement)
    *   `can_swim_on_surface`: `1`
    *   `can_dive`: `1`

*   **`CharacterPlatformingComponent`**:
    *   `fly_velocity_x`: `28` (Fast horizontal flight speed)

*   **`HitboxComponent`**:
    *   `aabb_max_x`: `7`, `aabb_max_y`: `3`
    *   `aabb_min_x`: `-7`, `aabb_min_y`: `-16` (Defines the enemy's collision box)

### `GenomeDataComponent`

*   `herd_id`: `slimes` (Belongs to the slime herd)
*   `food_chain_rank`: `9` (Relatively high on the food chain)
*   `is_predator`: `1` (Acts as a predator)

## Attack Behaviors

The Tentacler employs multiple `AIAttackComponent` instances to define its ranged attack patterns.

### Ranged Attack 1 (Primary)

*   **`AIAttackComponent`**:
    *   `min_distance`: `36`
    *   `max_distance`: `110`
    *   `frames_between`: `120`
    *   `attack_ranged_entity_file`: `data/entities/projectiles/smalltentacle.xml` (Fires a small tentacle projectile)
    *   `attack_ranged_offset_x`/`y`: `4`/`-7`

### Ranged Attack 2 (Freeze)

*   **`AIAttackComponent`**:
    *   `min_distance`: `0`
    *   `max_distance`: `38`
    *   `frames_between`: `80`
    *   `animation_name`: `attack_stone`
    *   `attack_ranged_entity_file`: `data/entities/projectiles/freeze_circle.xml` (Fires a freeze projectile)
    *   `attack_ranged_offset_y`: `-7`

### Ranged Attack 3 (Melee Tentacle)

*   **`AIAttackComponent`**:
    *   `min_distance`: `0`
    *   `max_distance`: `36`
    *   `frames_between`: `80`
    *   `attack_ranged_entity_file`: `data/entities/projectiles/smalltentacle_melee.xml` (Fires a melee tentacle projectile)
    *   `attack_ranged_offset_x`/`y`: `4`/`-7`

## Visual and Audio Components

*   **`HotspotComponent`**: Defines interaction points, likely for player interaction or targeting.
*   **`MaterialInventoryComponent`**:
    *   `leak_on_damage_percent`: `0.999` (Leaks materials when almost destroyed)
    *   `count_per_material_type`: `Material material="blood_fungi" count="800"` (Drops 800 units of fungi blood)
*   **`AudioComponent`**:
    *   `file`: `data/audio/Desktop/animals.bank`
    *   `event_root`: `animals/slime` (Defines the base sound events for the creature)
*   **`AudioLoopComponent`**:
    *   `event_name`: `animals/slimy_big/movement_loop` (Plays a continuous movement sound)

## Verlet Chains (Tentacles)

The Tentacler utilizes `verlet_chains` to animate its tentacles.

*   **`Entity`**:
    *   `Base file="data/entities/verlet_chains/smalltentacle/tentacler_tentacle_01.xml"` (Two instances of the first tentacle type)
    *   `Base file="data/entities/verlet_chains/smalltentacle/tentacler_tentacle_02.xml"` (One instance of the second tentacle type)
    *   `InheritTransformComponent` with varying `position.x` and `position.y` to position the tentacles.