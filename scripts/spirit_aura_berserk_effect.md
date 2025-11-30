---
title: Spirit Aura Berserk Effect
category: scripts
---

# Spirit Aura Berserk Effect

This script implements a berserk aura effect for spirits in Noita. When a spirit with this script is active, it searches for nearby entities tagged as "homing_target" or "player_unit". If a valid target is found that doesn't already have the "spirit_berserk" effect applied, it spawns an `effect_spirit_berserk.xml` entity as a child of the target. This effectively applies the berserk effect to nearby entities.

## Key Functionality

*   **Target Detection:** Scans a radius of 192 units around the spirit for entities with specific tags.
*   **Effect Application:** Spawns a visual/functional effect entity (`effect_spirit_berserk.xml`) on valid targets.
*   **Uniqueness Check:** Prevents applying the effect multiple times to the same root entity or to entities already possessing the "spirit_berserk" component.
*   **Exclusion:** Ignores entities tagged as "mimic_potion".

## Core Logic Breakdown

The script iterates through detected targets and checks for several conditions before applying the effect:

1.  **Self-Exclusion:** The spirit itself is not targeted.
2.  **Mimic Potion Exclusion:** Entities tagged "mimic_potion" are ignored.
3.  **Existing Effect Check:** It checks if the target entity or any of its children already have a `GameEffectComponent` with the tag "spirit_berserk". This prevents stacking the effect.
4.  **Root Entity Tracking:** Uses a `done` table to ensure the effect is applied only once per root entity.

## Key Attributes and Elements

*   `entity_id`: The ID of the spirit entity executing the script.
*   `x`, `y`: The transform coordinates of the spirit.
*   `r`: The radius (192) for detecting nearby entities.
*   `targets`: A table storing entities found with the "homing_target" tag.
*   `targets2`: A table storing entities found with the "player_unit" tag.
*   `done`: A table used to track root entities that have already received the berserk effect.
*   `EntityLoad("data/entities/misc/effect_spirit_berserk.xml", x, y)`: Loads the entity responsible for the berserk effect.
*   `EntityAddChild(v, eid)`: Attaches the loaded effect entity as a child to the target entity.
*   `EntityHasTag(v, "mimic_potion")`: Checks if an entity is a mimic potion.
*   `EntityGetComponent(b, "GameEffectComponent", "spirit_berserk")`: Checks for the presence of the berserk effect component.

## Related Files

*   `data/entities/misc/effect_spirit_berserk.xml`: The entity definition for the berserk effect itself.