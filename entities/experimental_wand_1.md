---
title: Experimental Wand 1
category: entities
---

# Experimental Wand 1

This document details the configuration for `experimental_wand_1.xml`, an experimental wand entity in Noita.

## Core Attributes

The `AbilityComponent` defines the fundamental behavior and properties of the wand.

### `AbilityComponent`

| Attribute              | Description                                                              | Value           |
| :--------------------- | :----------------------------------------------------------------------- | :-------------- |
| `amount_in_inventory`  | Initial quantity of the wand when found.                                 | `1`             |
| `cooldown_frames`      | Time in frames before the wand can be used again after firing.           | `0`             |
| `drop_as_item_on_death`| Whether the wand drops as an item when the player dies.                  | `1` (True)      |
| `entity_count`         | Number of entities this wand can spawn or affect.                        | `1`             |
| `mana_charge_speed`    | Speed at which mana regenerates.                                         | `30`            |
| `mana_max`             | Maximum mana capacity of the wand.                                       | `100`           |
| `max_amount_in_inventory`| Maximum quantity of this wand that can be held in inventory.             | `1`             |
| `reload_time_frames`   | Time in frames to reload the wand's spell deck.                          | `0`             |
| `sprite_file`          | Path to the sprite definition for the wand.                              | `data/entities/items/wands/experimental/experimental_wand_1_sprite.xml` |
| `ui_name`              | The name displayed in the user interface.                                | `experimental_wand_1` |
| `use_gun_script`       | Indicates if the wand uses a gun script for its firing logic.            | `1` (True)      |

### `gun_config`

Configures the wand's spell deck and shuffling behavior.

| Attribute           | Description                                     | Value |
| :------------------ | :---------------------------------------------- | :---- |
| `shuffle_deck_when_empty` | Whether the spell deck shuffles when empty. | `0`   |
| `reload_time`       | Time in frames to reload the spell deck.        | `24`  |
| `deck_capacity`     | Number of spells the wand can hold.             | `3`   |

### `gunaction_config`

Controls the timing of firing actions.

| Attribute      | Description                               | Value |
| :------------- | :---------------------------------------- | :---- |
| `fire_rate_wait` | Time in frames to wait between shots.     | `10`  |

## Visual and Physical Components

These components define the wand's appearance and interaction with the game world.

### `HotspotComponent`

Defines the firing point for projectiles.

| Attribute | Description        | Value |
| :-------- | :----------------- | :---- |
| `offset.x`| X-axis offset.     | `9`   |
| `offset.y`| Y-axis offset.     | `-0.5`|

### `SpriteComponent`

Manages the visual representation of the wand.

| Attribute         | Description                                     | Value                                                               |
| :---------------- | :---------------------------------------------- | :------------------------------------------------------------------ |
| `image_file`      | Path to the sprite image.                       | `data/entities/items/wands/experimental/experimental_wand_1_sprite.xml` |
| `next_rect_animation` | Name of the animation for the next frame.     | `default`                                                           |
| `rect_animation`  | Name of the default rectangle animation.        | `default`                                                           |
| `z_index`         | Determines the rendering order.                 | `-1.5`                                                              |

### `SimplePhysicsComponent`

Handles basic physics interactions.

| Attribute | Description                               | Value  |
| :-------- | :---------------------------------------- | :----- |
| `_enabled`| Whether the physics component is active.    | `0` (False) |

## Scripting and Functionality

The `LuaComponent` enables custom behavior for the wand.

### `LuaComponent`

| Attribute            | Description                                                              | Value                                                              |
| :------------------- | :----------------------------------------------------------------------- | :----------------------------------------------------------------- |
| `execute_on_added`   | Whether the script should execute when the entity is added.              | `1` (True)                                                         |
| `remove_after_executed`| Whether the script should be removed after execution.                    | `1` (True)                                                         |
| `script_source_file` | Path to the Lua script file that controls the wand's behavior.           | `data/entities/items/wands/experimental/experimental_wand_1.lua` |

## Mana Regeneration

The `ManaReloaderComponent` manages how the wand replenishes its mana.

### `ManaReloaderComponent`

This component is present and enabled by default, allowing the wand to passively regenerate mana.