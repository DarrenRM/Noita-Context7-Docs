---
title: Curse Projectile Initialization
category: scripts
---

# Curse Projectile Initialization

This script handles the initialization and stacking logic for curse projectiles in Noita. It determines whether to create a new curse entity or extend the duration and damage of an existing one.

## Core Functionality

The primary goal of this script is to manage the "curse" effect applied by certain projectiles. It ensures that multiple curse applications don't create redundant entities but instead enhance the existing curse.

### Key Logic Flow

1.  **Get Entity Information**: Retrieves the current entity ID and its root entity.
2.  **Check for Existing Curse**: Determines if the root entity already has the `effect_CURSE` tag.
3.  **Prevent "Curse NOT"**: If the entity has the `curse_NOT` tag, the curse effect is prevented entirely.
4.  **New Curse Creation**:
    *   If no `effect_CURSE` tag exists, a new `curse.xml` entity is loaded and attached to the root.
    *   The `effect_CURSE` tag is added to the root entity.
    *   It attempts to retrieve the `projectile_who_shot` from the projectile's `VariableStorageComponent` and applies it to the new curse entity.
5.  **Existing Curse Enhancement**:
    *   If an `effect_CURSE` tag already exists, the script iterates through the root entity's children to find the existing curse entity.
    *   **Lifetime Extension**: The `LifetimeComponent` of the existing curse is reset to extend its duration by 300 frames.
    *   **Damage Stacking**: The `VariableStorageComponent` for `effect_curse_damage` is found, and its `value_float` is increased by 0.08.
6.  **Projectile Cleanup**: The original projectile entity that triggered this script is killed.

## Key Components and Tags

*   **`effect_CURSE` Tag**: Applied to the root entity to signify the presence of an active curse effect.
*   **`curse_NOT` Tag**: If present on the root entity, prevents any curse effects from being applied.
*   **`VariableStorageComponent`**:
    *   Used to store `projectile_who_shot` (integer) to track who applied the curse.
    *   Used to store `effect_curse_damage` (float) to manage the stacking damage of the curse.
*   **`LifetimeComponent`**: Manages the duration of the curse effect.

## Relevant Entities

*   **`data/entities/misc/curse.xml`**: The entity definition for the curse effect itself.

## Example Usage (Conceptual)

When a projectile with curse-applying properties hits an entity:

1.  This script runs on the projectile.
2.  If the target entity doesn't have a curse, a new `curse.xml` entity is spawned and linked.
3.  If the target entity already has a curse, its duration and damage are increased.
4.  The projectile is then destroyed.