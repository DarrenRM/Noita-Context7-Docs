---
title: Scavenger Shield Entity
category: entities
---

---

# Scavenger Shield Entity

This document details the `scavenger_shield.xml` entity, which defines the behavior and attributes of the Scavenger Shield creature in Noita.

## Core Attributes

The Scavenger Shield is a flying enemy with a focus on ranged attacks and self-preservation.

### Base Entity

Inherits from `data/entities/base_enemy_flying.xml`.

### ItemChestComponent

*   **level**: `2` - Indicates the loot tier provided by this enemy.

### AnimalAIComponent

This component governs the creature's AI and combat behavior.

*   **preferred_job**: `JobDefault` - Standard AI job.
*   **escape_if_damaged_probability**: `100` - Will always attempt to flee when damaged.
*   **attack_if_damaged_probability**: `0` - Will never attack when damaged.
*   **tries_to_ranged_attack_friends**: `1` - Will attempt to shoot its allies.
*   **creature_detection_range_x/y**: `400` - Horizontal and vertical range for detecting creatures.
*   **creature_detection_angular_range_deg**: `60` - Angular detection cone.
*   **attack_melee_enabled**: `0` - Melee attacks are disabled.
*   **attack_ranged_enabled**: `1` - Ranged attacks are enabled.
*   **attack_ranged_entity_file**: `data/entities/projectiles/shieldshot.xml` - The projectile used for ranged attacks.
*   **attack_ranged_frames_between**: `30` - Delay between ranged attacks.
*   **aggressiveness_min/max**: `90`/`100` - High aggressiveness.

### DamageModelComponent

Defines the creature's health and damage-related properties.

*   **hp**: `1.8` - Hit points of the creature.
*   **fire_probability_of_ignition**: `5` - Low chance of igniting from fire.
*   **blood_spray_material**: `blood` - The material used for blood effects.

### SpriteComponent

*   **image_file**: `data/enemies_gfx/scavenger_shield.xml` - Specifies the graphical assets for the creature.

### PathFindingComponent

*   **can_fly**: `1` - The creature is capable of flight.

### CharacterPlatformingComponent

Controls movement and physics.

*   **fly_velocity_x**: `28` - Horizontal flight speed.

### HitboxComponent

Defines the collision area for the creature.

*   **aabb_min_x/max_x**: `-5`/`5` - Horizontal bounds of the hitbox.
*   **aabb_min_y/max_y**: `-12`/`3` - Vertical bounds of the hitbox.

### LightComponent

*   **radius**: `50` - The radius of the light emitted by the creature.

### AudioComponent

*   **file**: `data/audio/Desktop/animals.bank` - The audio bank containing the creature's sounds.
*   **event_root**: `animals/scavenger` - The root event for scavenger sounds.