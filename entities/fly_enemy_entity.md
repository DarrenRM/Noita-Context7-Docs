---
title: Fly Enemy Entity
category: entities
---

# Fly Enemy Entity

This document details the configuration of the "Fly" enemy entity in Noita, focusing on attributes relevant for AI-assisted modding.

## Core Entity Configuration

The Fly entity inherits from `base_enemy_flying.xml`, providing a foundation for its flying behavior and AI.

### `Base` Component Attributes

*   **`ItemChestComponent`**:
    *   `level="4"`: Indicates the loot tier associated with this enemy.

*   **`AnimalAIComponent`**: This is the primary component governing the Fly's behavior.
    *   `preferred_job="JobDefault"`: The default AI job assigned to the Fly.
    *   `attack_melee_damage_min="0.4"`: Minimum damage dealt by melee attacks.
    *   `attack_melee_damage_max="0.6"`: Maximum damage dealt by melee attacks.
    *   `attack_dash_enabled="1"`: Enables the Fly to perform a dash attack.
    *   `attack_melee_impulse_multiplier="120"`: Controls the force of the melee attack's knockback.
    *   `attack_dash_distance="90"`: The distance the Fly will dash during an attack.
    *   `creature_detection_range_x="300"`: Horizontal range for detecting other creatures.
    *   `creature_detection_range_y="300"`: Vertical range for detecting other creatures.
    *   `food_material="blood"`: The type of material the Fly consumes for sustenance.
    *   `needs_food="1"`: Indicates that the Fly requires food to survive.
    *   `sense_creatures="1"`: Enables the Fly to sense nearby creatures.
    *   `can_fly="1"`: Confirms the Fly's ability to fly.
    *   `can_walk="0"`: The Fly cannot walk.

*   **`DamageModelComponent`**: Manages the Fly's health and damage-related properties.
    *   `hp="1.5"`: The Fly's health points.
    *   `fire_probability_of_ignition="0"`: The probability of catching fire is zero.
    *   `ragdoll_filenames_file="data/ragdolls/fly/filenames.txt"`: Specifies the files used for the Fly's ragdoll physics.

*   **`SpriteComponent`**: Defines the visual appearance of the Fly.
    *   `image_file="data/enemies_gfx/fly.xml"`: Points to the sprite definition file.

*   **`PathFindingComponent`**: Handles pathfinding logic.
    *   `can_fly="1"`: The Fly uses flying pathfinding.
    *   `can_walk="0"`: The Fly cannot use walking pathfinding.

*   **`PathFindingGridMarkerComponent`**:
    *   `marker_work_flag="16"`: A flag used in pathfinding grid calculations.

*   **`GenomeDataComponent`**: Provides genetic information for AI and ecosystem simulation.
    *   `herd_id="fly"`: Identifies the herd or species.
    *   `food_chain_rank="10"`: Its position in the food chain.
    *   `is_predator="1"`: The Fly is a predator.

*   **`CharacterPlatformingComponent`**: Governs movement and physics.
    *   `fly_speed_max_up="100"`: Maximum upward flight speed.
    *   `fly_speed_max_down="100"`: Maximum downward flight speed.
    *   `fly_speed_mult="20"`: Multiplier for flight speed.
    *   `fly_speed_change_spd="1"`: Speed at which flight speed changes.
    *   `pixel_gravity="200"`: The effect of gravity on the Fly in pixels per frame.
    *   `fly_velocity_x="40"`: Base horizontal flight velocity.

*   **`CameraBoundComponent`**: Controls how the entity interacts with the camera's view.
    *   `max_count="30"`: Maximum number of this entity that can be active within the camera's bounds.
    *   `distance="160000"`: The radius around the camera within which this entity can exist.

*   **`HitboxComponent`**: Defines the collision area for interactions.
    *   `aabb_max_x="6"`: Maximum X-axis extent of the hitbox.
    *   `aabb_max_y="8"`: Maximum Y-axis extent of the hitbox.
    *   `aabb_min_x="-6"`: Minimum X-axis extent of the hitbox.
    *   `aabb_min_y="-6"`: Minimum Y-axis extent of the hitbox.

*   **`CharacterDataComponent`**: General character properties.
    *   `collision_aabb_min_x="-4.0"`: Minimum X-axis extent for collision.
    *   `collision_aabb_max_x="4.0"`: Maximum X-axis extent for collision.
    *   `collision_aabb_min_y="-11"`: Minimum Y-axis extent for collision.
    *   `collision_aabb_max_y="3"`: Maximum Y-axis extent for collision.
    *   `mass="1.0"`: The mass of the character.

### `AudioLoopComponent`

*   **`file="data/audio/Desktop/animals.bank"`**: Specifies the audio bank containing the sound event.
*   **`event_name="animals/wing_flap_insect/movement_loop"`**: The name of the sound event for wing flapping.
*   **`set_speed_parameter="1"`**: The sound's playback speed is linked to the entity's movement speed.
*   **`auto_play="1"`**: The sound starts playing automatically when the entity is spawned.