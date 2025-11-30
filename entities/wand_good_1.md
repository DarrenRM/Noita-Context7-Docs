---
title: Wand Good 1
category: entities
---

# Wand Good 1

This document details the configuration for `wand_good_1`, a basic wand entity in Noita, intended for AI-assisted modding.

## Entity Definition

The core entity definition for `wand_good_1`.

```xml
<Entity tags="wand,wand_good">
    <!-- Components detailing wand behavior and appearance -->
</Entity>
```

## Key Components

### AbilityComponent

This component governs the wand's core magical abilities, including mana, cooldowns, and projectile behavior.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `mana_max`            | Maximum mana capacity of the wand.                                          |
| `mana_charge_speed`   | Speed at which mana regenerates.                                            |
| `cooldown_frames`     | Time in frames before the wand can fire again (0 means no cooldown).        |
| `reload_time_frames`  | Time in frames to reload the wand's spell deck.                             |
| `drop_as_item_on_death` | If set to 1, the wand will drop as an item when the player dies.            |
| `sprite_file`         | Path to the XML file defining the wand's visual sprite.                     |
| `ui_name`             | Internal identifier for the wand, used in UI elements.                      |
| `use_gun_script`      | If 1, indicates that the wand uses a script for its firing logic.           |

#### `gun_config`

Nested within `AbilityComponent`, this defines the wand's spell deck mechanics.

| Attribute         | Description                                       |
| :---------------- | :------------------------------------------------ |
| `deck_capacity`   | The number of spells the wand can hold at once.   |
| `reload_time`     | Time in frames to reload the spell deck.          |
| `shuffle_deck_when_empty` | If 1, the deck shuffles when it becomes empty. |

#### `gunaction_config`

Nested within `AbilityComponent`, this controls the timing of firing actions.

| Attribute      | Description                                      |
| :------------- | :----------------------------------------------- |
| `fire_rate_wait` | Minimum frames to wait between shots.            |

### HotspotComponent

Defines the origin point for projectiles when the wand is fired.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `offset.x` | Horizontal offset from the wand's center. |
| `offset.y` | Vertical offset from the wand's center.   |

### Base Component

This component inherits properties from a base item, providing fundamental item functionalities.

#### `ItemComponent`

Specific item properties.

| Attribute           | Description                               |
| :------------------ | :---------------------------------------- |
| `item_name`         | The unique name of the item.              |
| `play_hover_animation` | If 1, the item plays a hover animation. |

#### `SpriteComponent`

Defines the visual representation of the item in the game world and inventory.

| Attribute       | Description                                      |
| :-------------- | :----------------------------------------------- |
| `image_file`    | Path to the image file for the sprite.           |
| `z_index`       | Controls the rendering order of the sprite.      |
| `rect_animation`| Specifies the animation to use for the sprite.   |

### LuaComponent

This component allows for custom scripting to extend the wand's functionality.

| Attribute                | Description                                                              |
| :----------------------- | :----------------------------------------------------------------------- |
| `script_source_file`     | Path to the Lua script file that controls the wand's behavior.           |
| `execute_on_added`       | If 1, the script executes when the entity is added to the game.          |
| `remove_after_executed`  | If 1, the LuaComponent is removed after the script has executed once.    |
| `script_item_picked_up`  | Path to a Lua script executed when the item is picked up by the player. |

### ManaReloaderComponent

This component enables the wand to automatically reload its mana over time.

```xml
<ManaReloaderComponent 
    _tags="enabled_in_world,enabled_in_hand,enabled_in_inventory" >
</ManaReloaderComponent>
```