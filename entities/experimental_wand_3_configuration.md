---
title: Experimental Wand 3 Configuration
category: entities
---

---

# Experimental Wand 3 Configuration

This document details the configuration for an experimental wand entity in Noita, focusing on its core attributes for AI-assisted modding.

## Wand Properties

This section outlines the primary characteristics of the wand.

| Attribute           | Value                               | Description                                                                 |
| :------------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `name`              | `{"It's a wand, ok?"}`              | A randomized UI name for the wand.                                          |
| `deck_capacity`     | `2`                                 | The number of spells that can be held in the wand's deck.                   |
| `actions_per_round` | `1`                                 | The number of spell actions that can be performed per wand firing cycle.    |
| `reload_time`       | `{3, 3}`                            | The minimum and maximum time (in frames) to reload the wand.                |
| `shuffle_deck_when_empty` | `0`                             | Determines if the deck is shuffled when empty (0 = no, 1 = yes).            |
| `fire_rate_wait`    | `3`                                 | The base delay (in frames) between firing actions.                          |
| `spread_degrees`    | `10`                                | The angular spread (in degrees) of projectiles fired by the wand.           |
| `speed_multiplier`  | `2.0`                               | A multiplier applied to the projectile speed.                               |
| `mana_charge_speed` | `{500, 500}`                        | The minimum and maximum speed at which mana charges.                        |
| `mana_max`          | `{1200, 1500}`                      | The minimum and maximum capacity of mana the wand can hold.                 |

## Component Configuration

This section details how specific components of the wand entity are configured.

### AbilityComponent

Configures the wand's magical abilities and UI representation.

*   **`ui_name`**: Set to a random name from the `gun.name` table.
*   **`mana_charge_speed`**: Randomized value from `gun.mana_charge_speed`.
*   **`mana_max`**: Randomized value from `gun.mana_max`.
*   **`mana`**: Initialized to the `mana_max` value.

### GunConfig (via `ComponentObjectSetValue`)

Configures the core mechanics of the wand's firing system.

*   **`reload_time`**: Randomized value from `gun.reload_time`.
*   **`actions_per_round`**: Set to `gun.actions_per_round`.
*   **`deck_capacity`**: Set to `gun.deck_capacity`.
*   **`shuffle_deck_when_empty`**: Set to `gun.shuffle_deck_when_empty`.

### GunActionConfig (via `ComponentObjectSetValue`)

Configures the specific actions and behaviors during firing.

*   **`fire_rate_wait`**: Set to `gun.fire_rate_wait`.
*   **`spread_degrees`**: Set to `gun.spread_degrees`.
*   **`speed_multiplier`**: Set to `gun.speed_multiplier`.

## Special Actions

*   **`AddGunActionPermanent( entity_id, "FUNKY_SPELL" )`**: Permanently adds a special "FUNKY\_SPELL" action to the wand.

## ItemComponent Configuration

Configures the wand as an item within the game's inventory system.

*   **`item_name`**: Set to `"$item_wand_experimental_1"`.
*   **`always_use_item_name_in_ui`**: Set to `true`, ensuring the item name is always displayed in the UI.