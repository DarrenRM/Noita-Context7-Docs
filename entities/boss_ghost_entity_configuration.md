---
title: Boss Ghost Entity Configuration
category: entities
---

# Boss Ghost Entity Configuration

This document details the configuration of the Boss Ghost entity in Noita, focusing on key attributes relevant to AI-assisted modding.

## Core Entity Properties

The Boss Ghost is a formidable enemy with several defining tags and components.

*   **Tags:** `enemy`, `teleportable_NOT`, `hittable`, `mortal`, `boss`, `touchmagic_immunity`, `music_energy_100`, `miniboss`, `polymorphable_NOT`, `necrobot_NOT`, `glue_NOT`, `curse_NOT`. These tags define its fundamental behavior, immunities, and role within the game.
*   **Name:** `$animal_boss_ghost` (localized name).
*   **ItemChestComponent:** `level="4"`, `enemy_drop="1"`. Indicates a high-tier loot drop.

## Visual Components

The Boss Ghost's appearance is constructed from multiple sprite components.

*   **SpriteComponent (Body):**
    *   `image_file="data/entities/animals/boss_ghost/body.xml"`
    *   `emissive="1"`, `additive="1"`: Contributes to its glowing, ethereal appearance.
    *   `z_index="0.9"`: Ensures it renders above other elements.
*   **SpriteComponent (Eye):**
    *   `image_file="data/entities/animals/boss_ghost/eye.xml"`
    *   `emissive="1"`
    *   `z_index="0.8"`
*   **SpriteComponent (Pupil):**
    *   `image_file="data/entities/animals/boss_ghost/pupil.xml"`
    *   `emissive="1"`
    *   `z_index="0.7"`
    *   **LuaComponent:** `script_source_file="data/entities/animals/boss_ghost/eye.lua"`, `execute_every_n_frame="1"`. Controls eye animations and behavior.

## AI and Movement

The `AnimalAIComponent` and `PathFindingComponent` govern the Boss Ghost's behavior and movement.

### AnimalAIComponent

*   **AI Behavior:**
    *   `preferred_job="JobDefault"`
    *   `creature_detection_range_x="300"`, `creature_detection_range_y="300"`: Large detection radius.
    *   `attack_dash_enabled="0"`: Does not perform dash attacks.
    *   `attack_ranged_enabled="1"`: Capable of ranged attacks.
    *   `attack_ranged_entity_file="data/entities/animals/boss_ghost/boss_ghost_polyp.xml"`: Ranged attack projectile.
    *   `attack_ranged_frames_between="60"`: Cooldown for ranged attacks.
    *   `food_material="blood"`, `needs_food="1"`: Consumes blood for sustenance.
    *   `sense_creatures="1"`, `sense_creatures_through_walls="1"`: Can detect creatures through walls.
    *   `can_fly="1"`: Capable of flight.
    *   `aggressiveness_min="1"`, `aggressiveness_max="100"`: Full range of aggressiveness.

### PathFindingComponent

*   **Movement Capabilities:**
    *   `can_dive="1"`, `can_fly="1"`, `can_swim_on_surface="1"`: Highly mobile in various environments.
    *   `can_jump="0"`, `can_walk="0"`: Does not utilize jumping or walking.
    *   `cost_of_flying="500"`: High cost associated with flying.
    *   `initial_jump_max_distance_x="100"`, `initial_jump_max_distance_y="60"`: Parameters for jump mechanics (though `can_jump` is 0, these might be legacy or for specific internal logic).

## Combat and Damage

The `DamageModelComponent` and `HitboxComponent` define its combat properties.

### DamageModelComponent

*   **Health and Resistances:**
    *   `hp="40.5"`: Moderate health pool.
    *   `ragdoll_material="rock_static_glow"`: Defines the material for its ragdoll effect.
    *   `blood_material="plasma_fading"`, `blood_spray_material="plasma_fading"`: Ethereal blood effects.
    *   `air_needed="0"`, `falling_damages="0"`: Immune to suffocation and fall damage.
*   **Damage Multipliers:**
    *   `projectile="0.0"`: Immune to projectile damage.
    *   `explosion="0.5"`: Takes half damage from explosions.
    *   `fire="0.5"`: Takes half damage from fire.
    *   `ice="0.0"`: Immune to ice damage.
    *   `slice="0.1"`: Takes minimal damage from slicing.
    *   `holy="0.5"`: Takes half damage from holy sources.

### HitboxComponent

*   `aabb_min_x="-16"`, `aabb_max_x="16"`, `aabb_min_y="-16"`, `aabb_max_y="16"`: Defines its collision box.
*   `is_enemy="1"`: Identifies it as an enemy.

### DamageNearbyEntitiesComponent

*   `radius="16"`: Damages entities within a 16-unit radius.
*   `damage_type="DAMAGE_CURSE"`: Applies curse damage.
*   `damage_description="$ethereal_damage"`: Uses a specific ethereal damage description.

## Physics and Visual Effects

*   **PhysicsAIComponent:** Manages its physics-based movement and interactions.
*   **PhysicsBodyComponent:** Defines its physical properties, including `fixed_rotation="1"`.
*   **ParticleEmitterComponent:** Emits `spark_blue_dark` particles for visual flair.
*   **AudioLoopComponent:** Plays `animals/ghost/movement_loop` for ambient sound.

## Special Abilities and Components

*   **Laser Emitters:** The entity contains multiple `LaserEmitterComponent` instances, configured to fire beams with specific damage and particle effects. These are controlled by `data/entities/animals/boss_ghost/lasers.lua`.
*   **GameEffectComponent:** Grants immunity to various status effects:
    *   `PROTECTION_FREEZE`
    *   `STUN_PROTECTION_ELECTRICITY`
    *   `PROTECTION_PROJECTILE`
*   **Lua Components:**
    *   `data/scripts/animals/ethereal_check.lua`: Handles ethereal checks.
    *   `data/entities/animals/boss_ghost/damage.lua`: Custom damage handling.
    *   `data/entities/animals/boss_ghost/helpers.lua`: General helper functions.
    *   `data/entities/animals/boss_ghost/death.lua`: Logic for when the boss dies.
*   **Health Bar:** Includes `SpriteComponent`s for `health_bar_back` and `health_bar` along with `BossHealthBarComponent` for UI display.