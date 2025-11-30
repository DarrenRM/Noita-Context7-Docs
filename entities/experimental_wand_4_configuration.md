---
title: Experimental Wand 4 Configuration
category: entities
---

---

# Experimental Wand 4 Configuration

This document details the configuration for `experimental_wand_4.lua`, an entity file defining a specific wand in Noita. It focuses on the key attributes that determine the wand's behavior and appearance.

## Core Wand Properties

These are the fundamental attributes that define the wand's performance.

| Attribute           | Value                               | Description                                                                 |
| :------------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `name`              | `{"$item_chainsaw"}`                | The internal name identifier for the wand, likely linked to its visual/UI.  |
| `deck_capacity`     | `1`                                 | The number of spells that can be held in the wand's deck.                   |
| `actions_per_round` | `1`                                 | The number of spell actions that can be performed per wand firing cycle.    |
| `reload_time`       | `[1, 1]`                            | The minimum and maximum time (in frames) to reload the wand.                |
| `shuffle_deck_when_empty` | `0`                             | Whether the deck is shuffled when it becomes empty (0 = false, 1 = true).   |
| `fire_rate_wait`    | `1`                                 | The base delay (in frames) between firing actions.                          |
| `spread_degrees`    | `30`                                | The angular spread of projectiles fired by the wand.                        |
| `speed_multiplier`  | `4.0`                               | A multiplier affecting the speed of projectiles.                             |
| `mana_charge_speed` | `[200, 300]`                        | The range for the wand's mana charge speed.                                 |
| `mana_max`          | `[800, 900]`                        | The range for the wand's maximum mana capacity.                             |

## Permanent Gun Actions

These are special actions that are permanently attached to the wand, influencing its behavior beyond standard spell casting.

*   **`RECOIL_DAMPER`**: Reduces or negates recoil.
*   **`BLOODLUST`**: Likely grants benefits when the player is low on health.
*   **`CHAINSAW`**: Implies a close-range, high-damage, or continuous attack effect.

## Item Component Configuration

This section details how the wand is presented as an item within the game's UI and inventory.

| Attribute              | Value               | Description                                                              |
| :--------------------- | :------------------ | :----------------------------------------------------------------------- |
| `item_name`            | `"$item_chainsaw"`  | The display name of the item in the UI.                                  |
| `always_use_item_name_in_ui` | `true`              | Ensures the `item_name` is always used for display, overriding other logic. |