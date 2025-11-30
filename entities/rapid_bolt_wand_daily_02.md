---
title: Rapid Bolt Wand (Daily 02)
category: entities
---

# Rapid Bolt Wand (Daily 02)

This entity defines a specific wand item in Noita, designed for rapid projectile firing. It's intended for use in daily challenges or as a pre-configured wand.

## Key Attributes

This wand is characterized by its high fire rate and specific configuration for projectile behavior.

### Base Item and Wand Configuration

*   **`base_item.xml`**: Inherits fundamental item properties.
    *   `SpriteComponent`: Defines the visual appearance and animations.
    *   `ItemComponent`: Handles player interaction, such as picking up and hovering.
    *   `SimplePhysicsComponent`: Disabled, indicating it doesn't have independent physics when not held.
*   **`base_wand.xml`**: Inherits core wand mechanics.

### `AbilityComponent` - Wand Functionality

This component dictates the wand's core firing and mana mechanics.

| Attribute                     | Value | Description                                                                 |
| :---------------------------- | :---- | :-------------------------------------------------------------------------- |
| `ui_name`                     | `Rapid bolt wand` | The name displayed in the game UI.                                          |
| `mana_max`                    | `200` | Maximum mana capacity of the wand.                                          |
| `mana_charge_speed`           | `60`  | Speed at which mana regenerates.                                            |
| `cooldown_frames`             | `0`   | No cooldown between shots (handled by `gunaction_config`).                  |
| `reload_time_frames`          | `0`   | No explicit reload time (handled by `gun_config`).                          |
| `shooting_reduces_amount_in_inventory` | `0` | The wand does not disappear from inventory after firing.                    |
| `drop_as_item_on_death`       | `1`   | The wand will be dropped as an item when the player dies.                   |
| `sprite_file`                 | `data/items_gfx/machinegun.xml` | Specifies the graphical asset for the wand's sprite.                        |
| `use_gun_script`              | `1`   | Indicates that a custom script (`LuaComponent`) controls the gun behavior. |

#### `gun_config`

Configures the wand's projectile deck and firing pattern.

| Attribute             | Value | Description                                                              |
| :-------------------- | :---- | :----------------------------------------------------------------------- |
| `deck_capacity`       | `8`   | The maximum number of spells that can be in the wand's "deck".           |
| `reload_time`         | `18`  | Time in frames to reload the wand's deck.                                |
| `shuffle_deck_when_empty` | `1` | The spell deck is shuffled when it becomes empty.                        |
| `actions_per_round`   | `1`   | Number of actions (spells) fired per "round" of shooting.                |

#### `gunaction_config`

Fine-tunes the timing of firing actions.

| Attribute       | Value | Description                                     |
| :-------------- | :---- | :---------------------------------------------- |
| `fire_rate_wait` | `5`   | Frames to wait between firing actions (shots). |

### `HotspotComponent`

Defines the origin point for projectiles.

*   `offset.x`: `20`
*   `offset.y`: `0`

### `LuaComponent` - Custom Scripting

This component executes a custom Lua script to define the wand's unique behavior.

*   `script_source_file`: `data/scripts/gun/procedural/wand_daily_02.lua`
    *   This script is responsible for the specific firing patterns and spell combinations that make this wand unique.
*   `execute_on_added`: `1`
*   `remove_after_executed`: `1`

### `ManaReloaderComponent`

Enables mana regeneration for the wand when it's in the world, in hand, or in inventory.

## Summary

The "Rapid Bolt Wand (Daily 02)" is a pre-configured wand designed for rapid-fire gameplay. Its `AbilityComponent` and associated `gun_config` and `gunaction_config` are tuned for a high rate of fire, with a small deck capacity and minimal delay between shots. The specific projectile behavior is determined by the `wand_daily_02.lua` script, making it a distinct and potentially challenging item for daily runs.