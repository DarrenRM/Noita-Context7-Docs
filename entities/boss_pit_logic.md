---
title: Boss Pit Logic
category: entities
---

# Boss Pit Logic

This document details the AI logic for the Boss Pit entity in Noita, focusing on its combat behaviors and projectile spawning.

## Core Functionality

The `boss_pit_logic.lua` script controls the actions of the Boss Pit, primarily its attack patterns and projectile usage. It utilizes a state machine based on a `VariableStorageComponent` to determine its behavior.

## Key Components and Attributes

### Hitbox Component

-   **`damage_multiplier`**: This attribute is dynamically adjusted. If the current multiplier is less than 1.0, it's increased by 0.35, capped at 1.0. This suggests a mechanic where the boss becomes more vulnerable over time or after certain conditions are met.

### Variable Storage Component

This component stores various states and memory for the Boss Pit.

-   **`state` (integer)**: Represents the current behavior state of the boss. The script cycles through states `0` to `9` using the modulo operator.
    -   **State 1**: Triggers projectile spawning.
    -   **State 7**: Triggers projectile spawning, with a chance to spawn "blackhole" projectiles if the boss is stuck.
-   **`memory` (string)**: Stores the path to a projectile to be used. If empty, it defaults to `data/entities/projectiles/enlightened_laser_darkbeam.xml`.
-   **`pathfinding_frames_stuck` (integer)**: Tracks how many frames the boss has been unable to move. Used to trigger alternative attack patterns.

### Entity State Management

-   **`EntitySetComponentsWithTagEnabled( entity_id, "invincible", false )`**: Ensures the boss is not invincible at the start of its logic execution.

## Attack Patterns

The Boss Pit exhibits different attack patterns based on its `state` variable.

### State 1: Projectile Barrage

When `state` is 1, the boss attempts to shoot projectiles.

-   **Projectile Selection**: A random projectile from a predefined list is chosen:
    -   `"rocket"`
    -   `"rocket_tier_2"`
    -   `"rocket_tier_3"`
    -   `"grenade"`
    -   `"grenade_tier_2"`
    -   `"grenade_tier_3"`
    -   `"rubber_ball"`
-   **Projectile Spawning**: A projectile is fired from the boss's location with a random angle and velocity.
-   **Wand Configuration**: The spawned projectile uses `data/entities/animals/boss_pit/wand.xml` as its base.
-   **Homing Component**: The spawned projectile is given a `HomingComponent` to target `player_unit` with a `homing_targeting_coeff` of `30.0` and `homing_velocity_multiplier` of `0.16`.
-   **Damage Multiplier**:
    -   If the projectile path contains "rocket", a `VariableStorageComponent` with `name = "mult"` and `value_float = 0.5` is added.
    -   Otherwise, a `VariableStorageComponent` with `name = "mult"` and `value_float = 1.2` is added.

### State 7: Orb/Blackhole Barrage

When `state` is 7, the boss has a chance to attack with orbs or blackholes.

-   **Random Chance**: There's a chance (`Random(1, 10) == 5`) or a guaranteed execution (`1 == 1`) for this state's actions.
-   **Stuck Behavior**: If `pathfinding_frames_stuck` is greater than 160, the boss will spawn `data/entities/projectiles/remove_ground.xml` projectiles (effectively blackholes) at its location with no initial velocity. This is a defensive or aggressive measure when the boss is unable to navigate.
-   **Standard Orb Attack**: If not stuck, the boss spawns a volley of orbs.
    -   **Orb Selection**: A random orb from the following list is chosen:
        -   `"orb_poly"`
        -   `"orb_neutral"`
        -   `"orb_tele"`
        -   `"orb_dark"`
    -   **Volley Spawning**: Eight projectiles are fired in an arc with a random offset. The velocity is calculated to create a circular spread.

## Helper Functions

-   **`shoot_projectile( entity_id, path, x, y, vel_x, vel_y )`**: A utility function (likely from `utilities.lua`) used to spawn projectiles.
-   **`edit_component( entity_id, component_name, callback_function )`**: Modifies an existing component on an entity.
-   **`ComponentGetValue2( comp, value_name )`**: Retrieves a value from a component.
-   **`ComponentSetValue2( comp, value_name, value )`**: Sets a value on a component.
-   **`EntityAddComponent( entity_id, component_name, component_data )`**: Adds a new component to an entity.
-   **`EntityGetComponent( entity_id, component_name )`**: Retrieves components of a specific type from an entity.
-   **`EntityGetWithTag( tag_name )`**: Retrieves all entities with a given tag.
-   **`SetRandomSeed( x, y )`**: Seeds the random number generator based on entity position and frame number.