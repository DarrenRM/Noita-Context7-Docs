---
title: Big Frog Entity
category: entities
---

# Big Frog Entity

This document details the configuration of the "Big Frog" entity in Noita, focusing on its AI, combat, and physical attributes.

## Core Components

The Big Frog entity is built upon a `Base` entity, inheriting fundamental properties and extending them with specific behaviors and characteristics.

### `Base` Entity Configuration

The `Base` entity provides the foundational structure. Key components include:

*   **`ItemChestComponent`**: Indicates the frog can drop loot upon death. `level="1"` suggests a moderate tier of loot.
*   **`AnimalAIComponent`**: Governs the creature's behavior.
    *   `preferred_job="JobDefault"`: The frog's default behavior.
    *   `escape_if_damaged_probability="35"`: A 35% chance to flee when damaged.
    *   `attack_dash_enabled="1"`: Enables a dash attack.
    *   `attack_dash_damage="0.4"`: The dash attack deals 0.4 damage.
    *   `creature_detection_range_x="250"`, `creature_detection_range_y="250"`: Detects creatures within a 250-unit radius.
    *   `food_material="meat"`: The frog consumes "meat" as food.
    *   `needs_food="1"`: The frog requires food to survive.
    *   `sense_creatures="1"`: The frog is aware of other creatures.
    *   `attack_ranged_action_frame="4"`: The frame at which the ranged attack is initiated.
    *   `attack_ranged_min_distance="0"`, `attack_ranged_max_distance="250"`: The frog can attack at any range up to 250 units.
    *   `attack_ranged_entity_file="data/entities/projectiles/tongue.xml"`: The projectile used for ranged attacks is a tongue.
    *   `attack_ranged_offset_y="-8"`: The ranged attack originates 8 units below the frog's center.
    *   `attack_ranged_enabled="1"`: Ranged attacks are enabled.
    *   `attack_melee_enabled="0"`: Melee attacks are disabled.
    *   `defecates_and_pees="1"`: The frog produces waste.
*   **`DamageModelComponent`**: Defines the frog's health and damage resistances.
    *   `hp="2.2"`: The frog has 2.2 hit points.
    *   `ragdoll_material="meat_frog"`: The material used for its ragdoll.
    *   `damage_multipliers`: Modifiers for incoming damage types.
        *   `projectile="0.8"`: Takes 80% damage from projectiles.
        *   `fire="0.5"`: Takes 50% damage from fire.
        *   `slice="0.2"`: Takes 20% damage from slicing.
*   **`SpriteComponent`**: Handles the visual representation.
    *   `image_file="data/enemies_gfx/frog_big.xml"`: Specifies the sprite graphics file.
    *   `rect_animation="stand"`: Uses the "stand" animation by default.
*   **`PathFindingComponent`**: Manages movement and navigation.
    *   `distance_to_reach_node_x="20"`, `distance_to_reach_node_y="20"`: The desired proximity to navigation nodes.
    *   `can_swim_on_surface="1"`, `can_dive="1"`: The frog can navigate both on and under water.
    *   `can_jump="1"`: The frog can jump.
    *   `can_walk="0"`: The frog cannot walk.
*   **`GenomeDataComponent`**: Defines genetic traits.
    *   `herd_id="slimes"`: Belongs to the "slimes" herd.
    *   `food_chain_rank="10"`: A high rank in the food chain.
    *   `is_predator="1"`: The frog is a predator.
*   **`CharacterDataComponent`**: Defines physical properties for character interactions.
    *   `collision_aabb_min_x="-5.0"`, `collision_aabb_max_x="5.0"`: Defines the horizontal collision bounds.
    *   `collision_aabb_min_y="-4"`, `collision_aabb_max_y="3"`: Defines the vertical collision bounds.
    *   `mass="0.6"`: The frog's mass.
*   **`CharacterPlatformingComponent`**: Governs platforming physics.
    *   `jump_velocity_y="-12"`: The vertical velocity applied when jumping.
    *   `run_velocity="0"`: The frog does not have a running speed.
*   **`HitboxComponent`**: Defines the entity's hitbox for interactions.
    *   `is_enemy="1"`: This hitbox is for an enemy.

### `AudioComponent`

*   **`file="data/audio/Desktop/animals.bank"`**: Specifies the audio bank containing the frog's sounds.
*   **`event_root="animals/frog_big"`**: The root event name for the frog's audio cues.