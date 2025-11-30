---
title: Rapid Bolt Wand (Unshuffle 04)
category: entities
---

# Rapid Bolt Wand (Unshuffle 04)

This document details the configuration for the "Rapid bolt wand" entity in Noita, focusing on its properties as a wand item.

## Core Wand Properties

The wand is defined by its `AbilityComponent`, which governs its behavior when wielded and its inventory management.

### `AbilityComponent` Key Attributes:

| Attribute                 | Value | Description                                                                 |
| :------------------------ | :---- | :-------------------------------------------------------------------------- |
| `ui_name`                 | "Rapid bolt wand" | The name displayed in the game's user interface.                            |
| `sprite_file`             | `data/items_gfx/machinegun.xml` | Specifies the visual appearance of the wand.                                |
| `mana_max`                | `300` | The maximum mana capacity of the wand.                                      |
| `mana_charge_speed`       | `80`  | How quickly the wand recharges mana.                                        |
| `max_amount_in_inventory` | `1`   | The maximum number of this wand that can be held in the inventory.          |
| `drop_as_item_on_death`   | `1`   | If the player dies, this wand will be dropped as an item.                  |
| `use_gun_script`          | `1`   | Indicates that the wand's behavior is controlled by a script.               |

### `gun_config` Attributes:

This sub-element within `AbilityComponent` defines the wand's firing mechanics.

| Attribute              | Value | Description                                                                 |
| :--------------------- | :---- | :-------------------------------------------------------------------------- |
| `shuffle_deck_when_empty` | `0`   | The wand does *not* shuffle its spell deck when it becomes empty.           |
| `reload_time`          | `18`  | The number of frames required to reload the wand after firing.              |
| `deck_capacity`        | `8`   | The maximum number of spells that can be held in the wand's spell deck.     |

### `gunaction_config` Attributes:

This sub-element further refines the firing behavior.

| Attribute       | Value | Description                                                                 |
| :-------------- | :---- | :-------------------------------------------------------------------------- |
| `fire_rate_wait` | `5`   | The number of frames to wait between consecutive shots.                     |

## Visual and Physics Components

The wand inherits base properties from other XML files for its visual representation and physics.

### `Base` Files:

*   `data/entities/base_wand_physics.xml`: Provides fundamental physics properties for wands.
    *   `SpriteComponent`: Configures sprite animations, specifically `next_rect_animation="JobAbilityMachinegun"`.
    *   `ItemComponent`: Enables hover animations when the item is being inspected (`play_hover_animation="1"`).
*   `data/entities/base_wand.xml`: Provides general base properties for all wands.

## Scripting and Functionality

The wand's unique behavior, particularly its spell casting logic, is handled by a Lua script.

### `LuaComponent` Key Attributes:

| Attribute             | Value                                                      | Description                                                                                             |
| :-------------------- | :--------------------------------------------------------- | :------------------------------------------------------------------------------------------------------ |
| `script_source_file`  | `data/scripts/gun/procedural/wand_unshuffle_04.lua`        | The path to the Lua script that defines the wand's procedural generation and casting behavior.          |
| `execute_on_added`    | `1`                                                        | The script will execute automatically when the wand is added to the game world or player's inventory. |
| `remove_after_executed` | `1`                                                        | The `LuaComponent` will be removed after its initial execution.                                         |

## Other Components

*   `HotspotComponent`: Defines the `shoot_pos` (shooting position) with an offset of `x=20, y=0`.
*   `ManaReloaderComponent`: Enables mana regeneration for the wand when it's in various states (world, hand, inventory).