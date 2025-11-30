---
title: Necromancer Shop Initialization
category: scripts
---

---

# Necromancer Shop Initialization

This script handles the initialization logic for the Necromancer shop in Noita, specifically its behavior when the player has achieved peace with the gods.

## Core Logic

The primary function of this script is to conditionally load a "CHARM" effect for the player if a specific global game state is met.

### Conditional Charm Loading

*   **Condition:** The script checks if the global variable `TEMPLE_PEACE_WITH_GODS` is set to `"1"`. This likely signifies a state where the player has achieved peace with the gods within the game.
*   **Action:** If the condition is true, the script proceeds to load a "CHARM" effect onto the player's entity.

### Key Attributes/Elements

*   `GlobalsGetValue( "TEMPLE_PEACE_WITH_GODS" )`: Retrieves the value of the global game state variable.
*   `GetUpdatedEntityID()`: Obtains the unique identifier for the current entity being processed (likely the player).
*   `GetGameEffectLoadTo( entity_id, "CHARM", true )`: Applies the "CHARM" game effect to the specified `entity_id`. The `true` parameter likely indicates that this is a permanent or significant effect.