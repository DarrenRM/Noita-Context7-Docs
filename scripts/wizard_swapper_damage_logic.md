---
title: Wizard Swapper Damage Logic
category: scripts
---

# Wizard Swapper Damage Logic

This script defines the behavior when a "wizard swapper" entity receives damage. Its primary function is to swap positions with the entity that caused the damage, unless that entity has the "no_swap" tag.

## Key Functionality

### `damage_received` Function

This function is triggered when the wizard swapper entity takes damage.

*   **Parameters:**
    *   `damage`: The amount of damage received.
    *   `desc`: A description of the damage.
    *   `entity_who_caused`: The entity that inflicted the damage.
    *   `is_fatal`: A boolean indicating if the damage is fatal.

*   **Logic:**
    1.  **Check if Damager is Alive:** If the `entity_who_caused` is not alive, the function returns without performing any action.
    2.  **Check for "no_swap" Tag:** If the `entity_who_caused` has the "no_swap" tag, the function returns, preventing a swap. This is a mechanism to exclude certain entities (like `rock_curse`) from being swapped with.
    3.  **Get Entity Transforms:** It retrieves the current position (`xa`, `ya`) of the wizard swapper (`entity_a`) and the position (`xb`, `yb`) of the entity that caused the damage (`entity_b`).
    4.  **Swap Positions:** The positions of `entity_a` and `entity_b` are swapped using `EntitySetTransform`.
    5.  **Play Swap Sound:** A specific sound effect (`player_projectiles/swapper/swap`) is played at the original position of the wizard swapper.

## Key Attributes/Elements

*   **`EntityGetIsAlive( entity_who_caused )`**: Checks if the entity that caused the damage is currently alive.
*   **`EntityHasTag( entity_who_caused, "no_swap" )`**: Checks if the damaging entity possesses the "no_swap" tag, which prevents swapping.
*   **`GetUpdatedEntityID()`**: Retrieves the unique identifier for the entity running this script (the wizard swapper).
*   **`EntityGetTransform( entity_id )`**: Gets the X and Y coordinates of an entity's transform.
*   **`EntitySetTransform( entity_id, x, y )`**: Sets the X and Y coordinates of an entity's transform, effectively moving it.
*   **`GamePlaySound( bank, sound_name, x, y )`**: Plays a specified sound effect at given coordinates.

This script provides a simple yet effective "swap" mechanic triggered by damage, adding a unique interaction to combat scenarios involving the wizard swapper.