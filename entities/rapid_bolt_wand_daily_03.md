---
title: Rapid Bolt Wand (Daily 03)
category: entities
---

# Rapid Bolt Wand (Daily 03)

This document describes the configuration for the "Rapid bolt wand," a wand entity in Noita, specifically designated as `wand_daily_03.xml`. It is designed to be a fast-firing wand with a specific procedural generation script.

## Core Components

The wand is built upon several base entity files and incorporates specific components to define its behavior and appearance.

### Base Entity Files

*   **`data/entities/base_item.xml`**: Provides fundamental item properties, including sprite handling and basic physics.
*   **`data/entities/base_wand.xml`**: Inherits core wand functionalities.

### Key Attributes

The `AbilityComponent` defines the wand's primary characteristics:

| Attribute                 | Value | Description                                                                                                |
| :------------------------ | :---- | :--------------------------------------------------------------------------------------------------------- |
| `ui_name`                 | `Rapid bolt wand` | The name displayed in the game's user interface.                                                           |
| `mana_max`                | `200` | The maximum mana capacity of the wand.                                                                     |
| `mana_charge_speed`       | `60`  | The speed at which mana regenerates.                                                                       |
| `reload_time_frames`      | `0`   | No explicit reload time is set here, managed by `gun_config`.                                              |
| `drop_as_item_on_death`   | `1`   | The wand will be dropped as an item when the player dies.                                                  |
| `sprite_file`             | `data/items_gfx/machinegun.xml` | Specifies the graphical representation of the wand.                                                        |
| `use_gun_script`          | `1`   | Indicates that a custom script is used for gun behavior.                                                   |
| `max_amount_in_inventory` | `1`   | Only one of this wand can be held in the inventory.                                                        |

### Gun Configuration

The `gun_config` within the `AbilityComponent` fine-tunes the firing mechanics:

| Attribute             | Value | Description                                                                                                |
| :-------------------- | :---- | :--------------------------------------------------------------------------------------------------------- |
| `actions_per_round`   | `1`   | The number of actions (spells) cast per firing cycle.                                                      |
| `shuffle_deck_when_empty` | `1`   | The spell deck will be shuffled when it becomes empty.                                                     |
| `reload_time`         | `18`  | The time in frames it takes to reload the wand after firing all spells in its current deck.                |
| `deck_capacity`       | `8`   | The maximum number of spells that can be held in the wand's spell deck.                                    |

### Firing Rate

The `gunaction_config` controls the interval between shots:

| Attribute    | Value | Description                                                                                                |
| :----------- | :---- | :--------------------------------------------------------------------------------------------------------- |
| `fire_rate_wait` | `5`   | The number of frames to wait between consecutive shots. A lower value means faster firing.                 |

## Visual and Positional Data

### Sprite Component

*   `next_rect_animation`: `JobAbilityMachinegun` - Suggests an animation related to a machine gun ability.

### Hotspot Component

*   `_tags`: `shoot_pos` - Marks this component as the position from which projectiles are fired.
*   `offset.x`: `20` - The horizontal offset of the firing position from the wand's center.
*   `offset.y`: `0` - The vertical offset of the firing position from the wand's center.

## Scripting and Logic

### Lua Component

*   `script_source_file`: `data/scripts/gun/procedural/wand_daily_03.lua` - This is the core script responsible for the wand's unique procedural generation and firing behavior.
*   `execute_on_added`: `1` - The script executes immediately when the wand is added to the game.
*   `remove_after_executed`: `1` - The Lua component is removed after its initial execution.

## Other Components

*   **`SimplePhysicsComponent`**: Disabled (`_enabled="0"`), indicating that the wand does not have standard physics interactions.
*   **`ManaReloaderComponent`**: Enabled in various game states (`enabled_in_world`, `enabled_in_hand`, `enabled_in_inventory`), ensuring mana regeneration is active when appropriate.