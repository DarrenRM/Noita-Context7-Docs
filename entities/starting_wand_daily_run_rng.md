---
title: Starting Wand (Daily Run RNG)
category: entities
---

# Starting Wand (Daily Run RNG)

This entity defines a special starting wand used in daily runs. Its key feature is that its spells are procedurally generated each day via a Lua script.

## Key Components

### `AbilityComponent`

This component defines the core properties of the wand as an item that can be used.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `mana_max`                | The maximum mana the wand can hold (100).                                   |
| `mana_charge_speed`       | How quickly mana regenerates (30).                                          |
| `cooldown_frames`         | Cooldown between shots (0).                                                 |
| `reload_time_frames`      | Time to reload the wand (0).                                                |
| `drop_as_item_on_death`   | If the wand drops when the player dies (1 - yes).                           |
| `max_amount_in_inventory` | Maximum number of this item that can be held (1).                           |
| `ui_name`                 | The name displayed in the UI ("Bolt staff").                                |
| `use_gun_script`          | Indicates that this entity uses gun-related scripting (1 - yes).            |

#### `gun_config`

Specific configurations for the wand's gun mechanics.

| Attribute           | Description                                     |
| :------------------ | :---------------------------------------------- |
| `deck_capacity`     | The number of spells the wand can hold (3).     |
| `shuffle_deck`      | Whether the spell deck shuffles when empty (0). |
| `reload_time`       | Reload time in frames (24).                     |

#### `gunaction_config`

Configuration for the action of firing the wand.

| Attribute      | Description                               |
| :------------- | :---------------------------------------- |
| `fire_rate_wait` | Wait time between firing actions (10).    |

### `HotspotComponent`

Defines the position where projectiles originate from the wand.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `offset.x`| X-axis offset for the firing position (8).|
| `offset.y`| Y-axis offset for the firing position (-0.5).|

### `Base` (for `base_item.xml`)

Defines the fundamental properties of the wand as an item.

#### `ItemComponent`

| Attribute                | Description                                     |
| :----------------------- | :---------------------------------------------- |
| `item_name`              | Internal name of the item ("default_gun").      |
| `remove_on_death`        | If the item is removed upon player death (1).   |
| `collect_nondefault_actions` | If non-default actions are collected (1).       |

#### `SpriteComponent`

Defines the visual representation of the wand when it's an item.

| Attribute        | Description                                     |
| :--------------- | :---------------------------------------------- |
| `image_file`     | Path to the sprite image ("data/items_gfx/handgun.xml"). |
| `rect_animation` | The default animation for the sprite ("default"). |
| `next_rect_animation` | The next animation in sequence ("default").     |

### `LuaComponent`

This is the core component responsible for the daily run's procedural spell generation.

| Attribute            | Description                                                                 |
| :------------------- | :-------------------------------------------------------------------------- |
| `_enabled`           | If the component is active (1 - yes).                                       |
| `execute_on_added`   | If the script should run when the entity is added (1 - yes).                |
| `remove_after_executed`| If the Lua component should be removed after execution (1 - yes).           |
| `script_source_file` | The path to the Lua script that generates the wand's spells ("data/scripts/gun/procedural/starting_wand_daily.lua"). |

### `ManaReloaderComponent`

This component enables the wand to automatically reload mana.

## Summary

This entity is a template for a starting wand in Noita's daily runs. It's configured as a functional wand with specific mana and firing properties. The crucial aspect is the `LuaComponent` which points to a script responsible for dynamically populating the wand with spells each day, ensuring a unique experience for every daily run.