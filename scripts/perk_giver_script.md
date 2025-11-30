---
title: Perk Giver Script
category: scripts
---

---

# Perk Giver Script

This script is designed to be attached to an entity that, when activated, grants all available perks to the player. It's a utility script, likely for testing or debugging purposes.

## Functionality

The script performs the following actions:

1.  **Includes necessary libraries:** It loads `game_helpers.lua`, `utilities.lua`, `perk_list.lua`, and `perk.lua` for game and perk-related functions.
2.  **Gets player entity:** It identifies the player's entity ID.
3.  **Iterates through perk list:** It loops through all perks defined in `perk_list.lua`.
4.  **Grants perks:** For each perk, it calls `perk_pickup` to give the perk to the player. The `true` arguments in `perk_pickup` likely indicate that the perk is not a negative perk and is being granted directly.
5.  **Kills self:** After granting perks, the entity executing this script is destroyed.

## Key Elements

*   **`perk_list.lua`:** This external file is crucial as it contains the definition of all available perks. The script iterates through this list to grant them.
*   **`perk_pickup( 0, player_id, perk_id, false, false, true )`:** This is the core function call that grants a perk.
    *   The first `0` likely represents the entity that is *giving* the perk (in this case, it's not directly relevant as the script handles the logic).
    *   `player_id` is the identifier of the player receiving the perk.
    *   `perk_id` is the unique identifier of the perk to be granted.
    *   The `false, false, true` arguments control specific perk acquisition behaviors, with `true` likely enabling direct granting without negative effects or special conditions.
*   **`EntityKill( entity_id )`:** This ensures the perk-giving entity is removed from the game world after its task is complete.

## Usage Example (Conceptual)

To use this script, you would typically:

1.  Create an entity in the game world.
2.  Attach this `give_all_perks.lua` script to that entity.
3.  Trigger the entity (e.g., by walking into it, or via another script interaction).
4.  The player would then receive all perks defined in `perk_list.lua`.