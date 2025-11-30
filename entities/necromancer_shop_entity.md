---
title: Necromancer Shop Entity
category: entities
---

# Necromancer Shop Entity

This document details the `necromancer_shop` entity, a flying enemy with ranged attack capabilities and a unique shop-like function.

## Core Attributes

*   **`name`**: `$animal_necromancer_shop` - The internal identifier for this entity.
*   **`tags`**: `necromancer_shop,music_energy_100_near` - Tags used for identification and triggering game events. `music_energy_100_near` suggests a proximity-based music effect.

## Base Entity Inheritance

This entity inherits from `data/entities/base_enemy_flying.xml`, providing fundamental flying enemy behaviors.

### `ItemChestComponent`

*   **`level`**: `1` - Indicates the loot tier or quality of items this entity might drop.

### `AnimalAIComponent`

This component governs the AI behavior of the Necromancer Shop.

*   **`attack_ranged_enabled`**: `1` - Enables ranged attacks.
*   **`attack_ranged_frames_between`**: `40` - Cooldown in frames between ranged attacks.
*   **`attack_ranged_offset_x`**: `8`, **`attack_ranged_offset_y`**: `-12` - Offset from the entity's center for ranged attack origin.
*   **`attack_ranged_action_frame`**: `4` - The frame within the attack animation when the projectile is fired.
*   **`attack_ranged_min_distance`**: `40`, **`attack_ranged_max_distance`**: `300` - The range within which the entity will use its ranged attack.
*   **`creature_detection_range_x`**: `600`, **`creature_detection_range_y`**: `600` - The range at which the entity detects other creatures.
*   **`needs_food`**: `0` - This entity does not require food.
*   **`can_fly`**: `1` - Explicitly states the entity can fly.

### `DamageModelComponent`

Defines the health and damage resistances of the Necromancer Shop.

*   **`hp`**: `24` - The entity's hit points.
*   **`ragdoll_material`**: `meat_cursed_dry`, **`blood_material`**: `bone`, **`blood_spray_material`**: `bone` - Specifies materials for ragdoll and blood effects.
*   **`fire_probability_of_ignition`**: `0` - Cannot be ignited by fire.
*   **`damage_multipliers`**:
    *   `explosion`: `0.2` - Takes 20% damage from explosions.
    *   `electricity`: `0.5` - Takes 50% damage from electricity.
    *   `fire`: `0.1` - Takes 10% damage from fire.

### `PathFindingComponent`

*   **`can_fly`**: `1` - The pathfinding system should consider flight.
*   **`can_walk`**: `0` - The entity cannot walk.

### `SpriteComponent` (Main Graphics)

*   **`image_file`**: `data/enemies_gfx/necromancer_shop.xml` - The primary sprite sheet for the entity.

### `HitboxComponent`

Defines the collision boundaries for the entity.

*   **`aabb_min_x`**: `-6.5`, **`aabb_max_x`**: `6.5` - Horizontal bounds.
*   **`aabb_min_y`**: `-16.0`, **`aabb_max_y`**: `3` - Vertical bounds.
*   **`is_enemy`**: `1` - This hitbox belongs to an enemy.

### `GenomeDataComponent`

*   **`herd_id`**: `mage` - Assigns the entity to the "mage" herd group.

### `CharacterDataComponent`

*   **`collision_aabb_min_x`**: `-5.0`, **`collision_aabb_max_x`**: `5.0` - Collision bounds for character interactions.
*   **`collision_aabb_min_y`**: `-16`, **`collision_aabb_max_y`**: `3`
*   **`mass`**: `1.1` - The entity's mass.

### `CharacterPlatformingComponent`

Controls movement parameters.

*   **`fly_speed_max_up`**: `100`, **`fly_speed_max_down`**: `100` - Maximum vertical flight speeds.
*   **`fly_speed_mult`**: `20` - Multiplier for flight speed.
*   **`pixel_gravity`**: `200` - The strength of gravity affecting the entity.
*   **`fly_velocity_x`**: `40` - Horizontal flight speed.

## `LightComponent`

Adds a light source to the entity.

*   **`radius`**: `70` - The radius of the light.
*   **`r`**: `149`, **`g`**: `235`, **`b`**: `255` - Light color (a pale blue).

## `SpriteComponent` (Emissive)

*   **`image_file`**: `data/enemies_gfx/necromancer_shop_emissive.xml` - Sprite sheet for emissive effects.
*   **`emissive`**: `1`, **`additive`**: `1` - Enables additive blending for emissive rendering.
*   **`rect_animation`**: `walk` - Specifies the default animation for this sprite.

## `AIAttackComponent` (Two instances)

These components define the entity's attack patterns.

### Attack 1 (Long Range)

*   **`min_distance`**: `41`, **`max_distance`**: `300` - Engages at longer ranges.
*   **`frames_between`**: `40` - Cooldown.
*   **`animation_name`**: `attack_ranged` - Associated animation.
*   **`attack_ranged_entity_file`**: `data/entities/projectiles/orb_pink_big_explosive.xml` - The projectile fired.

### Attack 2 (Short Range)

*   **`min_distance`**: `0`, **`max_distance`**: `40` - Engages at closer ranges.
*   **`frames_between`**: `20` - Faster cooldown.
*   **`animation_name`**: `attack_ranged_fast` - Associated animation.
*   **`attack_ranged_entity_file`**: `data/entities/projectiles/orb_pink.xml` - The projectile fired.

## `AudioComponent`

*   **`file`**: `data/audio/Desktop/animals.bank` - The audio bank used.
*   **`event_root`**: `animals/necromancer_shop` - The root event for this entity's sounds.

## `AudioLoopComponent`

*   **`event_name`**: `animals/necromancer_shop/movement_loop` - The specific sound event for movement.
*   **`auto_play`**: `1` - The sound plays automatically.

## `LuaComponent`

*   **`script_source_file`**: `data/scripts/animals/necromancer_shop_init.lua` - The Lua script executed on entity addition, likely for initialization.

## `Entity` (Shield Component)

This nested entity creates an energy shield effect.

### `InheritTransformComponent`

*   **`position.x`**: `0`, **`position.y`**: `-12` - Positions the shield relative to the Necromancer Shop.

### `Base file="data/entities/misc/animal_energy_shield.xml"`

Inherits from a generic energy shield.

#### `EnergyShieldComponent`

*   **`recharge_speed`**: `0.4` - How quickly the shield recharges.
*   **`radius`**: `32.0` - The radius of the shield.

#### `ParticleEmitterComponent` (Multiple)

These components emit pink plasma particles to visualize the shield.

*   **`emitted_material_name`**: `plasma_fading_pink` - The material of the particles.
*   **`area_circle_radius`**: Varies between `32` and `32` to create the shield's visual effect.