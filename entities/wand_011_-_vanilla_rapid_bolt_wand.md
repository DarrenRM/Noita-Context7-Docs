---
title: Wand 011 - Vanilla Rapid Bolt Wand
category: entities
---

# Wand 011 - Vanilla Rapid Bolt Wand

This document details the configuration for a specific wand entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core entity definition for this wand.

```xml
<Entity 
  _version="1" 
  name="" 
  serialize="1" 
  tags="teleportable_NOT,item,wand" >
  <Base file="data/entities/items/wands/level_01/base_wand_level_1.xml" >
    <!-- ... AbilityComponent, HotspotComponent, SpriteComponent ... -->
  </Base>
</Entity>
```

## Key Attributes

### AbilityComponent

This component governs the wand's functionality, including its magical properties and how it's used.

| Attribute                 | Value        | Description                                                                 |
| :------------------------ | :----------- | :-------------------------------------------------------------------------- |
| `ui_name`                 | Vanilla Rapid bolt wand | The name displayed in the game UI.                                          |
| `sprite_file`             | `data/items_gfx/wands/wand_0374.png` | The visual sprite for the wand.                                             |
| `mana`                    | 250          | Initial mana capacity.                                                      |
| `mana_max`                | 250          | Maximum mana capacity.                                                      |
| `mana_charge_speed`       | 50           | Speed at which mana regenerates.                                            |
| `charge_wait_frames`      | 10           | Frames to wait before the next shot after a full charge.                    |
| `item_recoil_max`         | 1            | Maximum recoil applied to the player.                                       |
| `item_recoil_offset_coeff`| 1            | Coefficient for recoil offset.                                              |
| `item_recoil_recovery_speed`| 15           | Speed at which recoil recovers.                                             |
| `item_recoil_rotation_coeff`| 5            | Coefficient for recoil rotation.                                            |
| `rotate_in_hand`          | 1            | Whether the wand rotates in the player's hand.                              |
| `rotate_in_hand_amount`   | 1            | Amount of rotation in hand.                                                 |
| `rotate_hand_amount`      | 0.7          | Amount of hand rotation applied.                                            |
| `amount_in_inventory`     | 1            | Number of this item that can be held in inventory.                          |
| `max_amount_in_inventory` | 1            | Maximum number of this item that can be held in inventory.                  |
| `use_gun_script`          | 1            | Indicates that this wand uses a gun script for its behavior.                |

#### `gun_config`

Configures the wand's shooting mechanics.

| Attribute         | Value | Description                                   |
| :---------------- | :---- | :-------------------------------------------- |
| `deck_capacity`   | 2     | Number of spells the wand can hold.           |
| `reload_time`     | 26    | Time in frames to reload the wand.            |
| `actions_per_round`| 1     | Number of actions performed per shot.         |

#### `gunaction_config`

Defines the properties of the projectile or action fired by the wand.

| Attribute         | Value   | Description                                                                 |
| :---------------- | :------ | :-------------------------------------------------------------------------- |
| `action_mana_drain`| 10      | Mana cost per shot.                                                         |
| `speed_multiplier`| 1.02408 | Multiplier for projectile speed.                                            |
| `spread_degrees`  | -2      | Spread angle of the projectile. Negative values can mean tighter spread.    |
| `fire_rate_wait`  | 20      | Frames to wait between firing actions.                                      |
| `action_type`     | 0       | Type of action (0 typically means a projectile).                            |
| `action_unidentified_sprite_filename` | `data/ui_gfx/gun_actions/unidentified.png` | Sprite for unidentified actions. |

### HotspotComponent

Defines the point from which the wand shoots.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `offset.x`| 7     | X-coordinate offset of the shooting position. |
| `offset.y`| 0     | Y-coordinate offset of the shooting position. |

### SpriteComponent

Defines the visual representation of the wand.

| Attribute | Value                  | Description                               |
| :-------- | :--------------------- | :---------------------------------------- |
| `image_file`| `data/items_gfx/wands/wand_0374.png` | The sprite file for the wand. |
| `offset_x`| 1                      | X-coordinate offset for the sprite.       |
| `offset_y`| 3                      | Y-coordinate offset for the sprite.       |