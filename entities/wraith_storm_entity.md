---
title: Wraith Storm Entity
category: entities
---

---

# Wraith Storm Entity

This document details the configuration of the Wraith Storm entity in Noita, focusing on its combat, AI, and visual properties.

## Base Entity Configuration

The Wraith Storm inherits its core functionality from `base_enemy_flying.xml`.

### Key Components:

*   **`ItemChestComponent`**: Indicates the entity can drop loot upon defeat (level 1).
*   **`AnimalAIComponent`**:
    *   `attack_ranged_enabled`: `0` (Cannot perform ranged attacks).
    *   `attack_dash_enabled`: `0` (Cannot perform dash attacks).
    *   `needs_food`: `0` (Does not require food).
    *   `can_fly`: `1` (Capable of flight).
*   **`DamageModelComponent`**:
    *   `hp`: `18.75` (Hit points).
    *   `fire_probability_of_ignition`: `0` (Immune to ignition).
    *   `ragdoll_fx_forced`: `DISINTEGRATED` (Special disintegration effect on death).
    *   `ragdoll_material`: `plasma_fading` (Material for ragdoll effect).
    *   `blood_material`: `plasma_fading` (Blood material).
    *   `blood_spray_material`: `plasma_fading` (Blood spray material).
    *   `minimum_knockback_force`: `100000` (High knockback resistance).
    *   **`damage_multipliers`**:
        *   `projectile`: `0.3`
        *   `explosion`: `0.3`
        *   `electricity`: `0.0` (Immune to electricity).
        *   `fire`: `0.7`
        *   `slice`: `0.3`
        *   `ice`: `0.4`
        *   `holy`: `0.3`
*   **`PathFindingComponent`**:
    *   `can_fly`: `1`
    *   `can_walk`: `0` (Cannot walk).
*   **`SpriteComponent`**:
    *   `image_file`: `data/enemies_gfx/wraith_storm.xml` (Defines the entity's visual appearance).
*   **`GenomeDataComponent`**:
    *   `herd_id`: `mage` (Belongs to the 'mage' herd).
    *   `food_chain_rank`: `15`
    *   `is_predator`: `1`
*   **`HitboxComponent`**: Defines the entity's collision boundaries.
    *   `aabb_min_x`: `-7.0`, `aabb_max_x`: `7.0`
    *   `aabb_min_y`: `-7`, `aabb_max_y`: `7`
*   **`CharacterDataComponent`**:
    *   `climb_over_y`: `4`
    *   `collision_aabb_min_x`: `-2.0`, `collision_aabb_max_x`: `2.0`
    *   `collision_aabb_min_y`: `-6`, `collision_aabb_max_y`: `4`
    *   `mass`: `0.9`
*   **`AudioComponent`**:
    *   `file`: `data/audio/Desktop/animals.bank`
    *   `event_root`: `animals/wraith_storm`

## Additional Components

### Visual and Environmental Effects:

*   **`LightComponent`**:
    *   `radius`: `30`
    *   `r`, `g`, `b`: `99`, `180`, `205` (Light color).
    *   `offset_y`: `-9`
*   **`AudioLoopComponent`**:
    *   Plays `animals/wraith_storm/movement_loop` and `animals/wraith/electricity_loop` for ambient sound.
*   **`Entity` (Wraith Cape)**:
    *   Includes a separate entity for the wraith's cape, inheriting transform from the main entity.
*   **`SpriteComponent` (Fog of War)**:
    *   `image_file`: `data/particles/fog_of_war_hole.xml`
    *   `alpha`: `0.55`
    *   `fog_of_war_hole`: `1` (Creates a hole in the fog of war).

### Particle Emitters:

The Wraith Storm utilizes several `ParticleEmitterComponent` and `SpriteParticleEmitterComponent` for visual effects:

*   **Blue Sparks**: Emitted from the entity's center and around a radius, with varying counts and lifetimes.
    *   `emitted_material_name`: `spark_blue`
    *   `gravity.y`: `0.0`
    *   `velocity_always_away_from_center`: `11` (for inner sparks)
*   **Arc Particles**: Emitted periodically to simulate electrical arcs.
    *   `sprite_file`: `data/particles/arc.xml`
    *   `emission_interval_min_frames`: `12`, `emission_interval_max_frames`: `20`
*   **Area Indicator**: A visual indicator sprite.
    *   `image_file`: `data/particles/area_indicator_064_blue.png`
    *   `z_index`: `1.2`

### Scripting:

*   **`LuaComponent`**:
    *   `script_source_file`: `data/scripts/projectiles/projectile_thunder.lua`
    *   `execute_every_n_frame`: `1` (Likely related to its electrical attacks or effects).