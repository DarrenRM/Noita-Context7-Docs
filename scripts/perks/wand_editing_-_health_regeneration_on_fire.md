---
title: Wand Editing - Health Regeneration on Fire
category: scripts/perks
---

# Wand Editing - Health Regeneration on Fire

This script defines a perk that grants the player health regeneration based on how many times they have fired a wand. The amount of health regenerated is influenced by whether the wand shuffles its spell deck when empty.

## Core Functionality

The `wand_fired` function is triggered whenever a wand is fired. It calculates the health regeneration amount based on the number of shots fired and the wand's shuffle configuration.

### Key Attributes & Logic

*   **`wand_fired( wand_entity_id )`**: The main function that executes when a wand is fired.
    *   Retrieves the player's entity ID.
    *   Identifies the wand entity.
    *   Accesses the `AbilityComponent` of the wand.
    *   Reads `stat_times_player_has_shot` to determine the shot count.
    *   Reads `shuffle_deck_when_empty` to check if the wand shuffles.

*   **Health Regeneration Calculation**:
    *   **Non-Shuffler Wands**: Health regeneration is higher for the first few shots and decreases with subsequent shots.
        *   Shot 1: 10 health
        *   Shot 2: 5 health
        *   Shot 3: 3 health
        *   Shot 4: 2 health
        *   Shots 5-7: 1 health
    *   **Shuffler Wands**: Health regeneration is generally higher than non-shuffler wands, especially for the initial shots.
        *   Shot 1: 16 health
        *   Shot 2: 8 health
        *   Shot 3: 4 health
        *   Shot 4: 2 health
        *   Shots 5-7: 1 health
    *   The calculated `heal` value is then divided by 25, suggesting a scaling factor for the actual health restored.

*   **Player Health Update**:
    *   Finds the `DamageModelComponent` of the player.
    *   Calculates the `current_hp` by adding the `heal` amount to the existing health, ensuring it doesn't exceed `max_hp`.
    *   Updates the player's health using `ComponentSetValue2`.

*   **Limitations**:
    *   The regeneration effect is capped at 7 shots. Wands fired more than 7 times do not grant additional health.
    *   There is a placeholder comment `TODO( Petri ): Play heal effect to communicate this to player`, indicating that visual or audio feedback for the healing is not yet implemented in this script.

### Example Usage (Conceptual)

This script would typically be associated with a perk that the player can acquire. When the perk is active, any wand the player uses will trigger this health regeneration logic upon firing.

```lua
-- Example of how the perk might be defined elsewhere (not in this file)
-- This is a conceptual representation.

-- Perk definition might look something like this:
-- {
--     id = "health_regen_on_fire",
--     name = "Regenerative Fire",
--     description = "Gain health when firing your wands.",
--     script = "data/scripts/perks/no_wand_editing.lua", -- Points to this script
--     -- other perk attributes...
-- }
```