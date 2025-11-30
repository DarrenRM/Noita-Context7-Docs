---
title: Wand 012 - Bad Rapid Bolt Wand
category: entities
---

# Wand 012 - Bad Rapid Bolt Wand

This document describes the configuration for a specific wand entity in Noita, identified as `wand_012.xml`. This wand is designed to be a rapid-firing projectile weapon with a moderate mana capacity.

## Key Attributes

The primary configuration for this wand is handled within the `<AbilityComponent>` and its nested `<gun_config>` and `<gunaction_config>` elements.

### `<AbilityComponent>`

This component defines the core properties of the wand as an item that can be used by the player.

| Attribute                 | Value        | Description                                                                 |
| :------------------------ | :----------- | :-------------------------------------------------------------------------- |
| `ui_name`                 | Bad Rapid bolt wand | The name displayed in the game's UI.                                        |
| `mana`                    | 250          | The current mana available to the wand.                                     |
| `mana_max`                | 250          | The maximum mana the wand can hold.                                         |
| `mana_charge_speed`       | 49           | The speed at which mana regenerates.                                        |
| `charge_wait_frames`      | 10           | Frames to wait before the wand can be fired again after a full charge.      |
| `rotate_in_hand_amount`   | 1            | Controls how much the wand rotates in the player's hand.                    |
| `item_recoil_max`         | 1            | Maximum recoil applied when firing.                                         |
| `item_recoil_recovery_speed` | 15           | How quickly the recoil returns to its neutral position.                     |
| `sprite_file`             | data/items_gfx/wands/wand_0324.png | The visual sprite for the wand.                                             |

### `<gun_config>`

This nested element within `<AbilityComponent>` configures the wand's shooting mechanics.

| Attribute       | Value | Description                                                                 |
| :-------------- | :---- | :-------------------------------------------------------------------------- |
| `deck_capacity` | 6     | The number of spells the wand can hold in its "deck".                       |
| `reload_time`   | 50    | The time in frames it takes to reload the wand.                             |
| `actions_per_round` | 1 | The number of actions (spells) executed per shot.                           |

### `<gunaction_config>`

This element defines the properties of the projectile fired by the wand.

| Attribute         | Value   | Description                                                                 |
| :---------------- | :------ | :-------------------------------------------------------------------------- |
| `speed_multiplier` | 0.995504 | Multiplier applied to the projectile's base speed.                          |
| `spread_degrees`  | -2      | The spread angle of the projectiles. Negative values can cause convergence. |
| `fire_rate_wait`  | 14      | Frames to wait between firing individual projectiles within a single shot.    |
| `action_mana_drain` | 10      | Mana cost per action (spell cast).                                          |

## Other Components

### `<_Transform>`

This component defines the initial position and rotation of the wand entity in the game world.

| Attribute   | Value   | Description                               |
| :---------- | :------ | :---------------------------------------- |
| `position.x` | 2227    | X-coordinate of the wand's spawn.         |
| `position.y` | 221     | Y-coordinate of the wand's spawn.         |
| `rotation`  | -2.5571 | Initial rotation of the wand in degrees.  |

### `<HotspotComponent>`

Defines the point from which projectiles are fired.

| Attribute  | Value | Description                               |
| :--------- | :---- | :---------------------------------------- |
| `offset.x` | 9     | X-offset of the shooting position.        |
| `offset.y` | 0     | Y-offset of the shooting position.        |

### `<SpriteComponent>`

Defines the visual sprite for the wand when it's an item in the world.

| Attribute | Value                | Description                               |
| :-------- | :------------------- | :---------------------------------------- |
| `image_file` | data/items_gfx/wands/wand_0324.png | The sprite file for the wand. |
| `offset_x` | 1                    | X-offset for the sprite.                  |
| `offset_y` | 4                    | Y-offset for the sprite.                  |