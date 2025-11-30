---
title: Wand Level 03 Better (Rapid Bolt Wand)
category: entities
---

# Wand Level 03 Better (Rapid Bolt Wand)

This document describes the `wand_level_03_better.xml` entity, which represents a "Rapid Bolt Wand" in Noita. This wand is designed for rapid projectile firing.

## Core Components

This wand inherits from `base_item.xml` and `base_wand.xml`, providing fundamental item and wand functionalities.

### `AbilityComponent`

This component defines the core properties of the wand's magical abilities.

| Attribute             | Description                                                              | Value           |
| :-------------------- | :----------------------------------------------------------------------- | :-------------- |
| `ui_name`             | The name displayed in the game UI.                                       | Rapid bolt wand |
| `sprite_file`         | Specifies the graphical representation of the wand.                      | `items_gfx/machinegun.xml` |
| `mana_max`            | The maximum mana capacity of the wand.                                   | 300             |
| `mana_charge_speed`   | How quickly the wand recharges mana.                                     | 80              |
| `max_amount_in_inventory` | The maximum number of this wand that can be held.                        | 1               |
| `drop_as_item_on_death` | If the player dies, this wand will drop as an item.                      | 1               |
| `use_gun_script`      | Indicates that this wand uses a custom gun script for its behavior.      | 1               |

#### `gun_config`

Configuration specific to the wand's firing mechanism.

| Attribute             | Description                                                              | Value |
| :-------------------- | :----------------------------------------------------------------------- | :---- |
| `deck_capacity`       | The number of spells that can be held in the wand's spell deck.          | 8     |
| `reload_time`         | The time in frames it takes to reload the wand after firing.             | 18    |
| `shuffle_deck_when_empty` | If the spell deck is empty, it will be shuffled.                         | 1     |

#### `gunaction_config`

Configuration for the actions performed when firing the wand.

| Attribute      | Description                                     | Value |
| :------------- | :---------------------------------------------- | :---- |
| `fire_rate_wait` | The delay in frames between consecutive shots. | 5     |

### `HotspotComponent`

Defines the point from which projectiles are fired.

| Attribute | Description                               | Value |
| :-------- | :---------------------------------------- | :---- |
| `offset.x` | Horizontal offset of the firing position. | 20    |
| `offset.y` | Vertical offset of the firing position.   | 0     |

### `LuaComponent`

This component executes a Lua script to define the wand's procedural generation and behavior.

| Attribute             | Description                                                              | Value                                                 |
| :-------------------- | :----------------------------------------------------------------------- | :---------------------------------------------------- |
| `script_source_file`  | The path to the Lua script file that controls the wand's behavior.       | `data/scripts/gun/procedural/wand_level_03_better.lua` |
| `execute_on_added`    | The script will execute when the entity is added to the game world.      | 1                                                     |
| `remove_after_executed` | The Lua component will be removed after its initial execution.           | 1                                                     |

### `ManaReloaderComponent`

This component enables the wand to passively regenerate mana. It is enabled in various game states.