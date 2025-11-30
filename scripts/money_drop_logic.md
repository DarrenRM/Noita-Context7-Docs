---
title: Money Drop Logic
category: scripts
---

# Money Drop Logic

This script defines the logic for dropping money when an entity is destroyed. It calculates the amount of money to drop based on the entity's health, game state, and potential perks.

## Core Function: `do_money_drop`

This is the primary function responsible for calculating and spawning money entities.

### Key Parameters:

*   `amount_multiplier` (number): A multiplier applied to the base money amount.
*   `trick_kill` (boolean): Determines if special "blood money" drops should be considered.

### Key Logic and Attributes:

1.  **Trailer Mode Check:** Skips money drops if `GameGetIsTrailerModeEnabled()` is true.
2.  **`no_gold_drop` Check:** Prevents drops if the entity has a `VariableStorageComponent` with `no_gold_drop` set to true.
3.  **Base Amount Calculation:**
    *   Starts with a base `amount` of 1.
    *   If the entity has a `DamageModelComponent`, the `amount` is set to its `max_hp` (if greater than 1.0).
4.  **"Greed Curse" Perk:** Doubles the `amount` if the `greed_curse` flag is active and `greed_curse_gone` is not.
5.  **Multiplier Application:** The `amount` is multiplied by the `amount_multiplier` parameter.
6.  **Total Money Calculation:** `money = 10 * amount`.
7.  **World State Perks:**
    *   **`perk_gold_is_forever`:** If active, spawned gold entities will not have a removal timer.
    *   **`perk_trick_kills_blood_money`:** If `trick_kill` is true and this perk is active, "blood money" entities are spawned instead of regular gold.
    *   **`perk_hp_drop_chance`:** A chance to drop a health pickup (50 blood money) is calculated based on this perk and the `amount_multiplier`.
8.  **Money Entity Spawning:**
    *   The script iteratively spawns different denominations of gold entities (`goldnugget_10.xml`, `goldnugget_50.xml`, etc.) based on the remaining `money` value.
    *   Special handling for very large amounts: If `money` exceeds a threshold, a "gold statue" (`goldnugget_x.xml`) is spawned, and its value is set via a `VariableStorageComponent`.
9.  **"Exploding Gold" Perk:** If the `exploding_gold` flag is active, spawned gold entities are given a `CollisionTriggerComponent` and a `LuaComponent` to trigger an explosion on collision with an enemy.

## Death Handler

The `death` function is a simple wrapper that calls `do_money_drop` with default parameters (multiplier of 1, `trick_kill` set to false).

```lua
function death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )
	do_money_drop( 1, false )
end
```