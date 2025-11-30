---
title: Wizard Weaken Entity
category: entities
---

# Wizard Weaken Entity

This document details the `wizard_weaken.xml` entity, a type of enemy found in Noita. It focuses on its combat capabilities, AI behavior, and visual representation.

## Core Attributes

### `name`
- `$animal_wizard_weaken`: The internal identifier for this entity.

### `Base`
- `file="data/entities/base_enemy_basic.xml"`: Inherits fundamental properties from the basic enemy template.

## AI and Combat

### `AnimalAIComponent`
This component governs the creature's behavior and combat actions.

- `creature_detection_range_x`, `creature_detection_range_y`: Defines the detection radius for other creatures (400 units).
- `food_material`: Specifies the material it consumes (`blood`).
- `needs_food`: Set to `0`, indicating it does not require sustenance.
- `sense_creatures`: Set to `1`, meaning it actively detects nearby creatures.
- `attack_ranged_enabled`: Set to `1`, enabling ranged attacks.
- `can_fly`: Set to `1`, allowing flight.
- `attack_ranged_entity_file`: Points to the projectile used for ranged attacks (`data/entities/projectiles/orb_weaken.xml`).
- `attack_ranged_frames_between`: The number of frames between ranged attacks (120).
- `attack_ranged_max_distance`: The maximum range of its ranged attack (300 units).

### `DamageModelComponent`
Defines the entity's health and damage resistance.

- `hp`: Health points (12).
- `ragdoll_material`: The material used for its ragdoll when defeated (`meat_slime`).

### `CharacterPlatformingComponent`
Controls movement and platforming abilities.

- `jump_velocity_y`: The vertical velocity applied when jumping (-12).
- `run_velocity`: The horizontal movement speed (18).

## Visuals and Hitbox

### `SpriteComponent`
Manages the entity's visual appearance.

- `image_file`: The file containing the sprite's graphical data (`data/enemies_gfx/wizard_weaken.xml`).

### `HitboxComponent`
Defines the collision area for interactions.

- `aabb_min_x`, `aabb_max_x`: Defines the horizontal bounds of the hitbox (-4.5 to 4.5).
- `aabb_min_y`, `aabb_max_y`: Defines the vertical bounds of the hitbox (-10 to 3).

### `CharacterDataComponent`
Specifies collision properties for character interactions.

- `collision_aabb_min_x`, `collision_aabb_max_x`: Defines the horizontal bounds for character collision (-3.0 to 3.0).
- `collision_aabb_min_y`, `collision_aabb_max_y`: Defines the vertical bounds for character collision (-7 to 3).

## Other Components

### `ItemChestComponent`
- `level="2"`: Indicates the loot tier associated with this enemy.

### `PathFindingComponent`
- `can_jump="1"`: Allows the entity to jump during pathfinding.

### `GenomeDataComponent`
Provides genetic information for AI and world generation.

- `herd_id`: Identifies the group this creature belongs to (`mage`).
- `food_chain_rank`: Its position in the food chain (6).
- `is_predator`: Set to `1`, indicating it is a predator.

### `CameraBoundComponent`
Manages how the entity interacts with the camera's view.

- `max_count`: Maximum number of this entity that can be active within the camera's view (30).
- `distance`: The distance at which the entity is considered by the camera (160000).

### `ItemPickUpperComponent`
- `is_in_npc="1"`: Suggests it can interact with or be treated as an NPC in some contexts.

### `HotspotComponent`
- `sprite_hotspot_name="cape"`: Defines a specific point on the sprite, likely for attaching other entities like the cape.

### `AudioLoopComponent`
- `event_name="animals/wizard/movement_loop"`: Specifies the sound event for its movement.

### `AudioComponent`
- `event_root="animals/wizard"`: Sets the root event name for other wizard-related sounds.

### `Entity` (Cape)
- This nested entity defines the visual cape attached to the wizard.
- `VerletPhysicsComponent`: Manages the physics simulation for the cloth.
    - `cloth_color_edge`, `cloth_color`: Defines the colors of the cape.

### `Entity` (Game Effect)
- `GameEffectComponent`: Applies a specific game effect.
    - `effect="STUN_PROTECTION_ELECTRICITY"`: Grants immunity to electricity-based stun effects.
    - `frames="-1"`: The effect is permanent.