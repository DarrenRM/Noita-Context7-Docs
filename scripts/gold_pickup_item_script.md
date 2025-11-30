---
title: Gold Pickup Item Script
category: scripts
---

---

# Gold Pickup Item Script

This script defines the behavior of gold pickup items in Noita, handling how they are collected, their value, and any associated effects.

## Core Functionality

The primary function `item_pickup` is triggered when an entity (typically the player) collects a gold pickup item. It manages the following:

### Key Attributes & Logic

*   **`value`**: Determines the amount of gold the pickup is worth. This is loaded from the `VariableStorageComponent` and defaults to `10`.
*   **`hp_value`**: Represents a health bonus provided by the pickup. This is also loaded from `VariableStorageComponent` and defaults to `0`.
*   **Wallet Interaction**:
    *   Retrieves the player's current money using `WalletComponent` and `ComponentGetValue2()`.
    *   Adds the pickup's `value` to the player's total money.
    *   Updates the player's wallet with the new total using `ComponentSetValue2()`.
*   **Health Restoration**: If `hp_value` is greater than `0`, a portion (`0.5` multiplier) of this value is used to heal the player using `heal_entity()`.
*   **Visual Effects**: Spawns different particle effects based on the `value` of the gold pickup:
    *   `gold_pickup_huge.xml` for values > 500.
    *   `gold_pickup_large.xml` for values > 40.
    *   `gold_pickup.xml` for all other values.
*   **`EXTRA_MONEY` Game Effect**: Checks for any active "EXTRA\_MONEY" game effects on the player. If found, the pickup's `value` is doubled for each active effect.
*   **Item Destruction**: The collected item entity is destroyed using `EntityKill()`.

### VariableStorageComponent Usage

The script relies on `VariableStorageComponent` attached to the gold pickup entity to define its specific properties:

| Variable Name | Data Type   | Description                                  |
| :------------ | :---------- | :------------------------------------------- |
| `gold_value`  | `value_int` | The monetary value of the gold pickup.       |
| `hp_value`    | `value_float` | The health bonus provided by the pickup.     |

### Dependencies

*   `data/scripts/game_helpers.lua`
*   `data/scripts/lib/utilities.lua`