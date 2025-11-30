---
title: Base Apparition Entity
category: entities
---

# Base Apparition Entity

This document describes the `base_apparition.xml` entity, which serves as a foundational template for various "apparition" type enemies in Noita. It defines core behaviors, combat capabilities, and visual properties.

## Key Components and Attributes

### Base Entity Inheritance

This entity inherits from `data/entities/base_enemy_flying.xml`, meaning it automatically gains all the properties and behaviors defined in that base class, such as general enemy AI, movement, and combat framework.

### AnimalAIComponent

This component governs the AI and behavior of the apparition.

*   **`_enabled`**: Controls whether the AI component is active.
*   **`preferred_job`**: Sets the default task for the AI (e.g., `JobDefault`).
*   **`escape_if_damaged_probability`**: The chance (0-100) the apparition will attempt to flee when damaged. Set to `100` for immediate escape.
*   **`attack_melee_damage_min` / `attack_melee_damage_max`**: Defines the minimum and maximum damage dealt by melee attacks.
*   **`creature_detection_range_x` / `creature_detection_range_y`**: The horizontal and vertical distance at which the apparition can detect creatures.
*   **`creature_detection_angular_range_deg`**: The field of view (in degrees) for creature detection.
*   **`attack_melee_max_distance`**: The maximum distance at which melee attacks can be performed.
*   **`sense_creatures`**: Enables the AI to detect other creatures.
*   **`can_fly`**: Allows the apparition to fly.
*   **`attack_melee_enabled`**: Enables melee attacks.
*   **`aggressiveness_min` / `aggressiveness_max`**: Sets the range for the apparition's aggressiveness.

### DamageModelComponent

Manages the health, damage resistances, and how the entity reacts to damage.

*   **`hp`**: The current health points.
*   **`max_hp`**: The maximum health points.
*   **`ragdoll_fx_forced`**: The visual effect applied when the entity is defeated (e.g., `DISINTEGRATED`).
*   **`ragdoll_material`**: The material used for the ragdoll effect.
*   **`damage_multipliers`**: A nested element defining how much damage the entity takes from different sources.
    *   `melee`: Multiplier for melee damage.
    *   `projectile`: Multiplier for projectile damage.
    *   `explosion`: Multiplier for explosion damage.
    *   `electricity`: Multiplier for electricity damage.
    *   `ice`: Multiplier for ice damage.
    *   `fire`: Multiplier for fire damage.

### SpriteComponent

Defines the visual appearance of the apparition.

*   **`image_file`**: Path to the sprite's image file (e.g., `data/enemies_gfx/playerghost.xml`).
*   **`emissive`**: If `1`, the sprite emits light.
*   **`additive`**: If `1`, the sprite uses additive blending.
*   **`offset_x` / `offset_y`**: Adjusts the sprite's position.

### PathFindingComponent

Determines how the entity navigates the game world.

*   **`can_fly`**: Allows the entity to use flight for pathfinding.
*   **`can_walk`**: Disables walking for this entity.

### GenomeDataComponent

Provides information for genetic and herd-based behaviors.

*   **`herd_id`**: A unique identifier for the apparition's herd.
*   **`food_chain_rank`**: Its position in the food chain.
*   **`is_predator`**: Indicates if the apparition is a predator.

### CharacterPlatformingComponent

Controls movement parameters related to character physics.

*   **`fly_speed_change_spd`**: The speed at which the entity changes its flying speed.
*   **`fly_velocity_x`**: The horizontal velocity when flying.
*   **`run_velocity`**: The horizontal velocity when running (though `can_walk` is `0`, this might influence other movement types).

### CameraBoundComponent

Manages how the entity interacts with the camera's view.

*   **`max_count`**: The maximum number of this entity that can be active within the camera's bounds.
*   **`distance`**: The maximum distance from the camera the entity can exist.

### HitboxComponent

Defines the collision area of the apparition.

*   **`aabb_max_x` / `aabb_max_y`**: The maximum X and Y coordinates of the bounding box.
*   **`aabb_min_x` / `aabb_min_y`**: The minimum X and Y coordinates of the bounding box.

### AudioComponent

Specifies the sound bank and event root for the entity's audio.

*   **`file`**: Path to the audio bank file.
*   **`event_root`**: The base event name for sounds associated with this entity.

### LightComponent

Adds a light source to the entity.

*   **`radius`**: The radius of the light emitted.
*   **`fade_out_time`**: How long it takes for the light to fade out.

### ItemPickUpperComponent

Enables the entity to pick up items.

*   **`is_in_npc`**: Indicates if this component is used by an NPC.

---