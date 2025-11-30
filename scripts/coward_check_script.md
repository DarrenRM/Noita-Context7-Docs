---
title: Coward Check Script
category: scripts
---

---

# Coward Check Script

This script controls whether an animal entity will enable its ranged attack based on its proximity to friendly targets.

## Purpose

The primary function of this script is to dynamically enable or disable the `attack_ranged_enabled` component for an `AnimalAIComponent`. This allows animals to act "cowardly" by only engaging in ranged combat when they are near allies.

## Key Components and Logic

### Entity Identification and Radius Check

-   **`entity_id`**: Retrieves the unique identifier for the current entity running this script.
-   **`x`, `y`**: Gets the current position of the entity.
-   **`radius`**: Defines the search radius (220 units) for potential targets.
-   **`EntityGetInRadiusWithTag(x, y, radius, "homing_target")`**: This function searches for entities within the specified radius that possess the "homing\_target" tag.

### Target Evaluation

-   The script iterates through the `targets` found within the radius.
-   For each potential target (`v`):
    -   It checks if the target is not the entity itself (`v ~= entity_id`).
    -   It retrieves the `GenomeDataComponent` to ensure it's a valid entity with genetic data.
    -   **`EntityGetHerdRelation(entity_id, v) >= 40`**: This is the crucial check. It determines if the herd relation between the current entity and the target is 40 or greater, indicating a friendly or allied relationship.
-   If a friendly target is found (`found = true`), the loop breaks.

### AI Component Modification

-   **`EntityGetFirstComponent(entity_id, "AnimalAIComponent")`**: Retrieves the `AnimalAIComponent` attached to the current entity.
-   **Conditional Attack Enablement**:
    -   If `found` is `true` (a friendly target is nearby), `attack_ranged_enabled` is set to `true`.
    -   If `found` is `false` (no friendly targets nearby), `attack_ranged_enabled` is set to `false`.

## Usage

This script is intended to be attached to animal entities that have an `AnimalAIComponent` and should exhibit conditional ranged attack behavior. The "homing\_target" tag should be applied to entities that are considered allies or targets for herd relation checks.