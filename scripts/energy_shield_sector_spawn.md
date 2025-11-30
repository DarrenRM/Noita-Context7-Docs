---
title: Energy Shield Sector Spawn
category: scripts
---

# Energy Shield Sector Spawn

This script defines the behavior for an entity that spawns and attaches an energy shield to a nearby enemy. It prevents multiple shields from being applied to the same enemy and slightly reduces the enemy's health to compensate for the shield.

## Key Functionality

*   **Targeting:** Identifies the closest entity with the "enemy" tag.
*   **Shield Application:** Attaches a child entity (assumed to be the shield) to the targeted enemy.
*   **Health Adjustment:** Reduces the target enemy's maximum HP by 45% (with a minimum reduction of 4 HP).
*   **Shield Activation:** Enables all components of the shield entity.
*   **Tagging:** Adds the "has_energy_shield" tag to the target enemy to prevent further shield applications.
*   **Self-Destruction:** The spawner entity is killed after successfully applying the shield.

## Core Logic Breakdown

The script primarily operates within the `collision_trigger` function (commented out in the provided snippet, but implied by the context of entity interaction).

### Entity Identification and Targeting

1.  **`GetUpdatedEntityID()`**: Retrieves the ID of the entity executing this script.
2.  **`EntityGetTransform(entity_id)`**: Gets the position (`x`, `y`) of the spawner entity.
3.  **`EntityGetClosestWithTag(x, y, "enemy")`**: Finds the nearest entity with the "enemy" tag to the spawner's position. If no enemy is found, the function returns.

### Shield Attachment and Prevention

1.  **`IsPlayer(target_id)`**: Checks if the identified target is a player. If it is, the script returns, as shields are intended for enemies.
2.  **`EntityGetAllChildren(entity_id)`**: Retrieves all child entities of the spawner. It's assumed the first child is the shield. If there are no children, the script returns.
3.  **`EntityHasTag(target_id, "has_energy_shield")`**: Checks if the target enemy already possesses an energy shield. If so, the spawner is killed to prevent duplicate shields.

### Health and Shield Component Manipulation

1.  **`component_readwrite(...)`**: This block targets the `DamageModelComponent` of the enemy.
    *   It reads the current `hp` and `max_hp`.
    *   It then writes new values: `max_hp` is set to 55% of its original value, but not less than `max_hp - 4`. `hp` is then set to this new `max_hp`. This effectively reduces the enemy's health.
2.  **`EntityGetAllComponents(shield_id)`**: Retrieves all components of the shield entity.
3.  **`EntitySetComponentIsEnabled(shield_id, comp, true)`**: Iterates through the shield's components and enables them, activating the shield.

### Finalization and Cleanup

1.  **`EntityRemoveFromParent(shield_id)`**: Detaches the shield from the spawner.
2.  **`EntityAddChild(target_id, shield_id)`**: Attaches the shield as a child to the targeted enemy.
3.  **`EntityAddTag(target_id, "has_energy_shield")`**: Marks the enemy as having a shield.
4.  **`EntityKill(entity_id)`**: Destroys the spawner entity.

## Key Attributes/Elements

| Attribute/Element          | Description