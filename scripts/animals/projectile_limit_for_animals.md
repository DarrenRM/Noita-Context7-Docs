---
title: Projectile Limit for Animals
category: scripts/animals
---

# Projectile Limit for Animals

This script limits the number of projectiles an animal can fire. It checks the number of projectiles within a specified radius around the animal and enables or disables ranged attacks based on a defined limit.

## Key Attributes

### `radius`
*   **Description:** The radius (in pixels) around the animal to check for existing projectiles.
*   **Type:** Number
*   **Default:** `220`

### `limit`
*   **Description:** The maximum number of projectiles allowed within the `radius` before ranged attacks are disabled.
*   **Type:** Number
*   **Default:** `15`

### `targets`
*   **Description:** A list of entities with the tag "projectile\_item" found within the specified `radius`.

### `comp`
*   **Description:** The `AnimalAIComponent` of the entity. This component is used to control the ranged attack capability.

## Logic

1.  **Get Entity Information:** Retrieves the current entity's ID, position (`x`, `y`), and the `AnimalAIComponent`.
2.  **Check Projectile Count:** It searches for entities tagged as "projectile\_item" within the defined `radius`.
3.  **Conditional Attack Enablement:**
    *   If the number of found projectiles (`#targets`) is less than the `limit`, the `attack_ranged_enabled` property of the `AnimalAIComponent` is set to `true`.
    *   If the number of found projectiles is equal to or greater than the `limit`, `attack_ranged_enabled` is set to `false`.