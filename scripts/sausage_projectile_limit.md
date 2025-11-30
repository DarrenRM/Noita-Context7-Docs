---
title: Sausage Projectile Limit
category: scripts
---

# Sausage Projectile Limit

This script controls the maximum number of "sausage" projectiles that can be active in the game world. It prevents an excessive number of these projectiles from being spawned, which can impact performance.

## Core Functionality

The `shot()` function is the primary logic for this script. It's designed to be called when a projectile is spawned or updated.

### Key Attributes

*   **`radius`**: Defines the area around the entity where it checks for existing "sausage" projectiles.
    *   Default: `220`
*   **`limit`**: The absolute maximum number of "sausage" projectiles allowed in the `radius`.
    *   Default: `15`
*   **`limitlocal`**: A stricter, local limit on the number of "sausage" projectiles the *current* entity can contribute to the overall count.
    *   Default: `12`

## Variable Storage

The script utilizes a `VariableStorageComponent` to track the number of "sausage" projectiles spawned by a specific entity.

### `sausage_max` Variable

*   **`name`**: `sausage_max`
    *   This is the identifier for the variable storing the projectile count.
*   **`value_int`**: An integer representing the current count of "sausage" projectiles spawned by this entity.

## AI Component Interaction

The script interacts with the `AnimalAIComponent` to enable or disable ranged attacks based on the projectile limits.

### `attack_ranged_enabled`

*   This boolean component value within `AnimalAIComponent` is toggled:
    *   `true`: If the number of projectiles is below the `limit` and `limitlocal`.
    *   `false`: If the number of projectiles reaches or exceeds the limits.

## Logic Flow

1.  **Get Entity Information**: Retrieves the current entity's ID and transform (position).
2.  **Check for `VariableStorageComponent`**: Searches for a component named `sausage_max` to get the current projectile count.
3.  **Find Nearby Projectiles**: Uses `EntityGetInRadiusWithTag` to find all entities with the tag `"projectile_item"` within the specified `radius`.
4.  **Evaluate Limits**:
    *   If the total number of nearby `"projectile_item"` entities is less than `limit` AND the current entity's `count` is less than `limitlocal`, then ranged attacks are enabled.
    *   Otherwise, ranged attacks are disabled.
5.  **Update Count**: The `value_int` of the `sausage_max` variable is updated with the current `count`.