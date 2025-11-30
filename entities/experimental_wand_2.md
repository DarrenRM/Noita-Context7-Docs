---
title: Experimental Wand 2
category: entities
---

# Experimental Wand 2

This document details the configuration for `experimental_wand_2`, an entity representing a wand in Noita, intended for AI-assisted modding.

## Entity Definition

The core of the wand is defined by the `<Entity>` tag, with specific tags indicating its type and experimental nature.

```xml
<Entity tags="wand,wand_experimental">
    <!-- ... components ... -->
</Entity>
```

## Key Components

### AbilityComponent

This component governs the wand's core functionality, including its magical properties and how it's used.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `amount_in_inventory` | Initial quantity of the wand when found.                                    |
| `cooldown_frames`     | Time in frames before the wand can be used again after firing.              |
| `drop_as_item_on_death` | Whether the wand drops as an item when the player dies.                     |
| `entity_count`        | Number of entities this wand can spawn (typically 1 for wands).             |
| `mana_charge_speed`   | Speed at which mana regenerates for the wand.                               |
| `mana_max`            | Maximum mana capacity of the wand.                                          |
| `max_amount_in_inventory` | Maximum number of this wand that can be held in the inventory.              |
| `reload_time_frames`  | Time in frames to reload the wand's spell deck.                             |
| `sprite_file`         | Path to the XML file defining the wand's visual appearance.                 |
| `ui_name`             | The name displayed in the game's user interface.                            |
| `use_gun_script`      | Indicates that the wand uses a script for its firing behavior.              |

#### `gun_config`

Nested within `AbilityComponent`, this defines the wand's spell-casting mechanics.

| Attribute           | Description                                     |
| :------------------ | :---------------------------------------------- |
| `shuffle_deck_when_empty` | Whether the spell deck is shuffled when empty.  |
| `reload_time`       | Time in frames to reload the spell deck.        |
| `deck_capacity`     | Number of spells the wand can hold in its deck. |

#### `gunaction_config`

Further refines the firing behavior.

| Attribute      | Description                                     |
| :------------- | :---------------------------------------------- |
| `fire_rate_wait` | Minimum frames to wait between shots.           |

### HotspotComponent

Defines the origin point for projectiles fired from the wand.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `offset.x`| X-axis offset from the wand's center.     |
| `offset.y`| Y-axis offset from the wand's center.     |

### Base Component

This component inherits common properties for items.

#### `ItemComponent`

Specific item-related attributes.

| Attribute             | Description                               |
| :-------------------- | :---------------------------------------- |
| `item_name`           | Internal name of the item.                |
| `play_hover_animation`| Whether to play a hover animation when held. |

#### `SpriteComponent`

Handles the visual rendering of the wand as an item.

| Attribute        | Description                                      |
| :--------------- | :----------------------------------------------- |
| `image_file`     | Path to the sprite image file.                   |
| `next_rect_animation` | Name of the animation to play next.            |
| `rect_animation` | Name of the current rectangle animation.         |
| `z_index`        | Determines the rendering order (layer).          |

### LuaComponent

This is crucial for custom wand behavior, linking to an external Lua script.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `execute_on_added`    | If true, the script runs immediately when the entity is added.              |
| `remove_after_executed` | If true, the LuaComponent is removed after the script finishes execution. |
| `script_source_file`  | Path to the Lua script file that controls the wand's behavior.              |

### ManaReloaderComponent

This component enables the wand to passively regenerate mana.

```xml
<ManaReloaderComponent
    _tags="enabled_in_world,enabled_in_hand,enabled_in_inventory" >
</ManaReloaderComponent>
```