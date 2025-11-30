---
title: Rapid Bolt Wand
category: entities
---

# Rapid Bolt Wand

This entity defines a specific wand item in Noita, designed for rapid projectile firing. It inherits base functionality from `base_item.xml` and `base_wand.xml`, with custom attributes defining its unique behavior.

## Key Attributes

### Item Component
- `play_hover_animation`: `1` - Enables a hover animation when the item is inspected.
- `has_been_picked_by_player`: `1` - Indicates this item is intended to be picked up by the player.

### Ability Component
This component governs the wand's magical properties and firing mechanics.

| Attribute                 | Value | Description                                                              |
| :------------------------ | :---- | :----------------------------------------------------------------------- |
| `amount_in_inventory`     | `1`   | The default number of this wand in the player's inventory.               |
| `cooldown_frames`         | `0`   | No cooldown between firing actions.                                      |
| `drop_as_item_on_death`   | `1`   | The wand will be dropped as an item when the player dies.                |
| `entity_count`            | `1`   | Not directly used for wand firing, but part of base item properties.     |
| `fast_projectile`         | `0`   | Projectiles are not inherently faster than normal.                       |
| `mana_charge_speed`       | `60`  | Speed at which mana regenerates.                                         |
| `mana_max`                | `200` | Maximum mana capacity of the wand.                                       |
| `max_amount_in_inventory` | `1`   | The maximum number of this wand that can be held in the inventory.       |
| `reload_time_frames`      | `0`   | No reload time between firing sequences.                                 |
| `shooting_reduces_amount` | `0`   | Firing does not consume a charge of the wand itself.                     |
| `sprite_file`             | `data/items_gfx/machinegun.xml` | Specifies the visual representation of the wand. |
| `ui_name`                 | `Rapid bolt wand` | The name displayed in the game's UI.                     |
| `use_gun_script`          | `1`   | Indicates that a custom script controls the wand's firing behavior.      |

#### Gun Configuration
- `actions_per_round`: `1` - Each firing action performs one "round" of shooting.
- `shuffle_deck_when_empty`: `1` - The spell deck is shuffled when it runs out of spells.
- `reload_time`: `18` - The time in frames to reload the spell deck.
- `deck_capacity`: `8` - The maximum number of spells that can be held in the wand's deck.

#### Gun Action Configuration
- `fire_rate_wait`: `5` - The minimum delay in frames between consecutive shots.

### Hotspot Component
- `_tags`: `shoot_pos` - Marks this as the position from which projectiles are fired.
- `offset.x`: `20` - The horizontal offset of the firing position from the wand's center.
- `offset.y`: `0` - The vertical offset of the firing position from the wand's center.

### Lua Component
- `_enabled`: `1` - The Lua script is active.
- `execute_on_added`: `1` - The script runs immediately when the entity is added.
- `remove_after_executed`: `1` - The Lua component is removed after its initial execution.
- `script_source_file`: `data/scripts/gun/procedural/wand_daily_06.lua` - The path to the custom Lua script that defines the wand's unique firing logic.

### Mana Reloader Component
- `_tags`: `enabled_in_world,enabled_in_hand,enabled_in_inventory` - This component is active in all states of the wand. It likely handles mana regeneration.