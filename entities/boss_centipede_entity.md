---
title: Boss Centipede Entity
category: entities
---

---

# Boss Centipede Entity

This document details the configuration for the Boss Centipede entity in Noita, focusing on key attributes relevant to AI-assisted modding.

## Core Attributes

The Boss Centipede is a formidable enemy with several defining characteristics.

*   **Name:** `$animal_boss_centipede`
*   **Tags:** `enemy`, `mortal`, `hittable`, `homing_target`, `boss_centipede`, `boss`, `polymorphable_NOT`, `teleportable_NOT`, `necrobot_NOT`, `glue_NOT`
    *   These tags define its behavior and interactions within the game world, such as being a target for homing projectiles, a boss-type enemy, and not being susceptible to polymorphing or teleportation.
*   **ItemChestComponent:** `level="4"`, `enemy_drop="1"`
    *   Indicates a high-level loot drop.

## Visuals

The Boss Centipede's appearance is managed by its `SpriteComponent`.

*   **SpriteComponent:**
    *   `image_file`: `data/entities/animals/boss_centipede/body.xml`
    *   `z_index`: `0.9` (Determines its rendering layer)

## AI and Behavior

The entity's AI is driven by several `LuaComponent`s and a `PathFindingComponent`.

*   **LimbBossComponent:** `state="1"`
    *   Likely controls the boss's limb-based mechanics.
*   **LuaComponent (Pre-Fight):**
    *   `script_source_file`: `data/entities/animals/boss_centipede/boss_centipede_before_fight.lua`
    *   Executes once when the entity is added.
*   **LuaComponent (Update):**
    *   `script_source_file`: `data/entities/animals/boss_centipede/boss_centipede_update.lua`
    *   `_enabled="0"` and `_tags="disabled_at_start"`: This script is likely activated later in the fight.
*   **LuaComponent (Test Check):**
    *   `script_source_file`: `data/entities/animals/boss_centipede/testcheck.lua`
    *   `execute_every_n_frame="5"`: Runs periodically for testing or specific checks.
*   **PathFindingComponent:**
    *   `can_dive="1"`, `can_fly="1"`, `can_swim_on_surface="1"`: Indicates advanced movement capabilities.
    *   `can_walk="0"`: The centipede does not walk.
    *   `cost_of_flying="500"`: High cost associated with flying, suggesting it's used strategically.
    *   Various parameters control search depth, iteration limits, and jump mechanics.

## Physics

The entity's physical properties are defined by `PhysicsBodyComponent`, `PhysicsShapeComponent`, and `PhysicsAIComponent`.

*   **PhysicsBodyComponent:**
    *   `fixed_rotation="1"`: The body does not rotate freely.
    *   `is_static="1"`: The main body is static, with movement likely handled by other components.
*   **PhysicsShapeComponent:**
    *   `is_circle="1"`, `radius_x="16"`, `radius_y="16"`: Defines a circular hitbox.
*   **PhysicsAIComponent:**
    *   `_enabled="0"` and `_tags="disabled_at_start"`: This component is likely activated during the fight to control physics-based movement.
    *   `force_coeff`, `torque_coeff`, and their balancing counterparts control movement forces.

## Damage and Health

The `DamageModelComponent` defines the centipede's health and how it takes damage.

*   **DamageModelComponent:**
    *   `hp`: `56.5`
    *   `blood_material`: `slime_green`
    *   `blood_spray_material`: `slime_green`
    *   `materials_that_damage`: `acid`
    *   `materials_how_much_damage`: `0.1`
*   **damage_multipliers:**
    *   `melee`: `2.0` (Takes double damage from melee)
    *   `projectile`: `0.3`
    *   `explosion`: `0.2`
    *   `electricity`: `0.1`
    *   `fire`: `0.1`
    *   `slice`: `1.0`
    *   `ice`: `0.1`
    *   `holy`: `0.2`
*   **HitboxComponent:**
    *   `_enabled="0"` and `_tags="disabled_at_start"`: This defines a central weak spot, likely activated during specific phases.
    *   `damage_multiplier`: `1.0`

## Audio

Multiple `AudioComponent`s and `AudioLoopComponent`s manage the centipede's soundscape.

*   **AudioComponent (General):** `event_root="animals"`
*   **AudioComponent (Specific):** `event_root="animals/boss_centipede"`
*   **AudioLoopComponent (Pre-Battle):** `event_name="animals/boss_centipede/prebattle_tinkering_loop"`
*   **AudioLoopComponent (Movement):** `event_name="animals/boss_centipede/movement_loop"`

## Entity Structure

The Boss Centipede is composed of several sub-entities, including limbs and a tail.

*   **Limbs:** Multiple instances of `data/entities/animals/boss_centipede/limbs/limb_long.xml`.
*   **Tail:** `data/entities/animals/boss_centipede/tail/tail.xml`.
*   **Verlet Chains:** Various `verlet_vine` and `verlet_vine_short/long.xml` entities are attached at specific offsets, likely for visual effect or physics interaction.
*   **Protection Entity:** A child entity with `GameEffectComponent` set to `PROTECTION_ALL`, providing a defensive buff.
*   **BossHealthBarComponent:** `gui_special_final_boss="1"` enables a special health bar for this boss.