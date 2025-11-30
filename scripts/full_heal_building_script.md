---
title: Full Heal Building Script
category: scripts
---

# Full Heal Building Script

This script defines the behavior for a "Full Heal" building in Noita. When activated, it restores the player's health to maximum, spawns a visual effect, and applies a short-term protection buff.

## Key Functionality

*   **Health Restoration:** Fully replenishes the player's health.
*   **Visual Feedback:** Spawns a "poof_green" particle effect at the building's location.
*   **Protection Buff:** Applies a temporary "effect_protection_all_short" to the player.
*   **Self-Destruction:** The building entity is removed after activation.

## Core Logic

The script performs the following steps:

1.  **Get Entity Information:** Retrieves the current entity ID and its root entity, along with its world coordinates.
2.  **Access Damage Component:** Locates the `DamageModelComponent` of the player's root entity.
3.  **Restore Health:** If the `DamageModelComponent` is found, it reads the `max_hp` and sets the current `hp` to this maximum value.
4.  **Spawn Effects:**
    *   Loads and spawns `data/entities/particles/poof_green.xml` at the player's location.
    *   Loads and spawns `data/entities/misc/effect_protection_all_short.xml` at the player's location and attaches it as a child to the player's root entity.
5.  **Remove Building:** The script then kills the building entity that executed this script.

## Relevant Components & Entities

*   **`DamageModelComponent`**: Essential for accessing and modifying health values.
*   **`data/entities/particles/poof_green.xml`**: Visual effect for healing.
*   **`data/entities/misc/effect_protection_all_short.xml`**: Applies a short-term protection buff.

## AI Modding Considerations

*   **Triggering:** This script is typically attached to a building entity that is triggered by player interaction or proximity.
*   **Customization:**
    *   The particle effect (`poof_green.xml`) can be swapped for different visual cues.
    *   The protection effect (`effect_protection_all_short.xml`) can be replaced with other buffs or removed entirely.
    *   The health restoration logic can be modified to heal only a percentage or to apply damage over time instead.
*   **Integration:** Ensure that the entity this script is attached to has the necessary components (e.g., interaction components) to be activated by the player.