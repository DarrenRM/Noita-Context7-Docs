---
title: Bat Entity Configuration
category: entities
---

# Bat Entity Configuration

This document details the configuration for the Bat entity in Noita, focusing on key attributes relevant for AI-assisted modding.

## Entity Definition

The Bat entity is defined by the `$animal_bat` tag. It inherits core functionalities from `base_enemy_flying.xml`.

## Core Components

### Base Enemy Flying Component

This component inherits from `base_enemy_flying.xml`, providing fundamental flying enemy behaviors.

*   **ItemChestComponent**: `level="2"` - Indicates the loot rarity or quality associated with this enemy.
*   **AnimalAIComponent**:
    *   `attack_ranged_enabled="0"`: Bats do not use ranged attacks.
    *   `attack_dash_enabled="1"`: Bats can perform dash attacks.
    *   `needs_food="0"`: Bats do not require food to survive.
    *   `can_fly="1"`: Confirms the entity's ability to fly.
*   **DamageModelComponent**:
    *   `hp="0.5"`: The bat has very low health.
    *   `ragdoll_filenames_file="data/ragdolls/bat/filenames.txt"`: Specifies the files used for the bat's ragdoll physics.
    *   `ragdoll_material="meat_slime"`: The material of the ragdoll.
    *   `blood_material="slime"`: The material of the blood.
    *   `blood_spray_material="slime"`: The material of the blood spray.
    *   `blood_sprite_directional`, `blood_sprite_large`: Paths to particle effects for blood splatters.
*   **PathFindingComponent**:
    *   `can_fly="1"`: The entity can navigate through flight.
    *   `can_walk="0"`: The entity cannot walk.
    *   `can_jump="0"`: The entity cannot jump.
*   **SpriteComponent**:
    *   `image_file="data/enemies_gfx/bat.xml"`: Specifies the graphical asset for the bat.
    *   `offset_x`, `offset_y`: Adjustments for sprite positioning.
*   **GenomeDataComponent**:
    *   `herd_id="bat"`: Identifies the species for herd behavior.
    *   `food_chain_rank="10"`: Indicates its position in the food chain.
    *   `is_predator="1"`: Marks the bat as a predator.
*   **HitboxComponent**:
    *   `aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`: Defines the bounding box for collision detection.
    *   `is_enemy="1"`, `is_item="0"`, `is_player="0"`: Specifies its role in gameplay.
*   **CharacterDataComponent**:
    *   `climb_over_y="4"`: Vertical distance the character can climb over.
    *   `collision_aabb_min_x`, `collision_aabb_max_x`, `collision_aabb_min_y`, `collision_aabb_max_y`: Defines the collision box for character interactions.
    *   `mass="0.6"`: The physical mass of the character.

### Light Component

*   **LightComponent**:
    *   `r="60"`, `g="30"`, `b="40"`: Defines the reddish-brown color of the light emitted by the bat.
    *   `radius="48"`: The radius of the light effect.

### Audio Components

The bat has two audio components, likely for different sound events:

*   **AudioComponent 1**:
    *   `file="data/audio/Desktop/animals.bank"`: The audio bank containing the sounds.
    *   `event_root="animals/bat"`: The root event for bat-specific sounds.
*   **AudioComponent 2**:
    *   `file="data/audio/Desktop/animals.bank"`: The same audio bank.
    *   `event_root="animals/wing_flap_skin"`: The root event for wing flap sounds.