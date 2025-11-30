---
title: Weaken Status Effect
category: scripts/status_effects
---

---

# Weaken Status Effect

This script defines the behavior for the "Weaken" status effect in Noita. When applied, it temporarily disables any "effect_protection" components on the player's entity.

## Key Attributes

*   **`weaken_start.lua`**: The primary script file for this status effect.
*   **`EntityGetParent( entity_id )`**: Retrieves the parent entity of the status effect, typically the player.
*   **`EntityGetAllChildren( player_id )`**: Gets all child entities of the player.
*   **`EntityHasTag( v, "effect_protection" )`**: Checks if a child entity has the "effect_protection" tag.
*   **`EntitySetComponentsWithTagEnabled( v, "effect_protection", false )`**: Disables components with the "effect_protection" tag on the specified entity.

## Functionality

The script iterates through all child entities of the player. If a child entity possesses the "effect_protection" tag, its corresponding components are disabled. This effectively removes any temporary protection the player might have had against other status effects.