---
title: Starting Bomb Wand (Daily Run)
category: entities
---

# Starting Bomb Wand (Daily Run)

This entity defines the "Bomb wand" item, specifically configured for daily runs. It's a basic wand that shoots bombs.

## Key Components and Attributes

### AbilityComponent

This component governs the wand's core functionality as a weapon.

| Attribute              | Value                               | Description                                                                 |
| :--------------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `amount_in_inventory`  | `1`                                 | The number of this item that can be held in the inventory.                  |
| `cooldown_frames`      | `0`                                 | No cooldown between shots.                                                  |
| `drop_as_item_on_death`| `1`                                 | The wand will drop as an item when the player dies.                         |
| `entity_count`         | `1`                                 | How many projectiles are fired per shot.                                    |
| `mana_charge_speed`    | `30`                                | Speed at which mana recharges.                                              |
| `mana_max`             | `100`                               | Maximum mana capacity of the wand.                                          |
| `max_amount_in_inventory`| `1`                                 | Maximum number of this item allowed in inventory.                           |
| `reload_time_frames`   | `0`                                 | No reload time between shots.                                               |
| `sprite_file`          | `data/items_gfx/bomb_wand.xml`      | The sprite used for the wand when held.                                     |
| `ui_name`              | `Bomb wand`                         | The name displayed in the UI.                                               |
| `use_gun_script`       | `1`                                 | Indicates that this entity uses a gun script for its behavior.              |

#### `gun_config`

| Attribute         | Value | Description                                     |
| :---------------- | :---- | :---------------------------------------------- |
| `reload_time`     | `24`  | Time in frames to reload the wand's spell deck. |
| `deck_capacity`   | `3`   | The number of spells that can be held in the wand's deck. |

#### `gunaction_config`

| Attribute     | Value | Description                               |
| :------------ | :---- | :---------------------------------------- |
| `fire_rate_wait`| `10`  | Minimum frames to wait between firing.    |

### HotspotComponent

Defines the position from which the wand shoots.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `offset.x`| `6`   | Horizontal offset of the shooting position. |
| `offset.y`| `-0.5`| Vertical offset of the shooting position. |

### Base Components

This entity inherits functionality from base item and wand pickup entities.

*   **`data/entities/base_item.xml`**: Provides general item properties like `item_name` and `remove_on_death`.
*   **`data/entities/base_wand_pickup.xml`**: Handles the behavior when the wand is picked up.
*   **`SpriteComponent`**: Defines the visual representation of the item in the world and inventory.

### LuaComponent

This is the core of the wand's unique behavior, especially for daily runs.

| Attribute          | Value                                                | Description