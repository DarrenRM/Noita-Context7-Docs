---
title: Spirit Aura Confuse Script
category: scripts
---

# Spirit Aura Confuse Script

This script defines the behavior for a "spirit aura" that confuses nearby entities. It identifies targets within a radius and applies a confusion effect to them, preventing them from being confused multiple times.

## Core Functionality

*   **Target Detection:** Scans for entities within a radius of `192` units. It specifically looks for entities with the `"homing_target"` tag and also includes `"player_unit"` entities.
*   **Confusion Application:** If a valid target is found (not the entity itself and not a mimic potion), it checks if the target already has the "spirit_confuse" game effect. If not, it loads and applies the `effect_spirit_confusion.xml` entity to the target as a child.
*   **Duplicate Prevention:** Uses a `done` table to ensure that each root entity is only confused once.

## Key Attributes and Elements

*   `entity_id`: The ID of the entity executing this script.
*   `x`, `y`: The current position of the entity.
*   `r`: The radius (192 units) within which targets are detected.
*   `targets`: A table storing entities with the `"homing_target"` tag.
*   `targets2`: A table storing entities with the `"player_unit"` tag.
*   `done`: A table used to track entities that have already been confused to prevent repeated application.
*   `EntityLoad("data/entities/misc/effect_spirit_confusion.xml", x, y)`: Loads the entity responsible for applying the confusion effect.
*   `EntityAddChild(v, eid)`: Attaches the confusion effect entity to the confused target.

## Logic Flow

1.  Get the current entity's ID and position.
2.  Define the detection radius `r`.
3.  Find all entities with `"homing_target"` tag within radius `r`.
4.  Find all entities with `"player_unit"` tag within radius `r`.
5.  Combine both sets of targets into a single `targets` table.
6.  Iterate through each `target`:
    *   Check if the target is not the script's entity and not a mimic potion.
    *   Check if the target's root entity has already been processed (using the `done` table).
    *   If the target is valid and not yet processed:
        *   Check if any of its children have the `"GameEffectComponent"` with `"spirit_confuse"`.
        *   If no existing confusion effect is found:
            *   Load the `effect_spirit_confusion.xml` entity at the target's position.
            *   Add the loaded effect entity as a child to the target.
            *   Mark the target as processed in the `done` table.