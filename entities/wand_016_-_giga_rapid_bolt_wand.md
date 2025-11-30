---
title: Wand 016 - Giga Rapid Bolt Wand
category: entities
---

# Wand 016 - Giga Rapid Bolt Wand

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

*   **`tags`**: `teleportable_NOT`, `item`, `wand` - Indicates this item is a wand, can be picked up, but cannot be teleported.

## Ability Component

This component defines the wand's core functionality and stats.

```xml
<AbilityComponent 
  _enabled="1" 
  amount_in_inventory="1" 
  charge_wait_frames="10" 
  cooldown_frames="0" 
  current_slot_durability="70" 
  entity_count="1" 
  is_petris_gun="0" 
  item_recoil_max="1" 
  item_recoil_offset_coeff="1" 
  item_recoil_recovery_speed="15" 
  item_recoil_rotation_coeff="5" 
  mana="750" 
  mana_charge_speed="10" 
  mana_max="750" 
  max_amount_in_inventory="1" 
  rotate_hand_amount="0.7" 
  rotate_in_hand="1" 
  rotate_in_hand_amount="1" 
  shooting_reduces_amount_in_inventory="0" 
  sprite_file="data/items_gfx/wands/wand_0830.png" 
  ui_name="Giga Rapid bolt wand" 
  use_gun_script="1" >

  <gun_config 
    actions_per_round="1" 
    deck_capacity="9" 
    reload_time="18" 
    shuffle_deck_when_empty="1" >
  </gun_config>

  <gunaction_config 
    action_mana_drain="10" 
    fire_rate_wait="26" 
    speed_multiplier="1.07678" 
    spread_degrees="-3" >
  </gunaction_config>

</AbilityComponent>
```

### Key Attributes:

*   **`charge_wait_frames`**: `10` - Delay between firing shots.
*   **`current_slot_durability`**: `70` - Initial durability of the wand.
*   **`mana`**: `750` - Current mana pool.
*   **`mana_max`**: `750` - Maximum mana pool.
*   **`mana_charge_speed`**: `10` - Rate at which mana regenerates.
*   **`sprite_file`**: `data/items_gfx/wands/wand_0830.png` - Visual representation of the wand.
*   **`ui_name`**: `Giga Rapid bolt wand` - The name displayed in the game's UI.
*   **`use_gun_script`**: `1` - Indicates this wand uses a script for its firing behavior.

### `gun_config`:

*   **`actions_per_round`**: `1` - Number of spell actions executed per shot.
*   **`deck_capacity`**: `9` - Maximum number of spells the wand can hold.
*   **`reload_time`**: `18` - Frames required to reload the wand.
*   **`shuffle_deck_when_empty`**: `1` - The wand's spell deck will be shuffled when it runs out of spells.

### `gunaction_config`:

*   **`action_mana_drain`**: `10` - Mana cost per spell action.
*   **`fire_rate_wait`**: `26` - Frames to wait between firing actions.
*   **`speed_multiplier`**: `1.07678` - Affects the projectile speed.
*   **`spread_degrees`**: `-3` - Negative spread value, indicating a tighter grouping of projectiles.

## Hotspot Component

Defines the firing position for the wand.

```xml
<HotspotComponent 
  _tags="shoot_pos" 
  offset.x="10" 
  offset.y="0" >
</HotspotComponent>
```

*   **`offset.x`**: `10` - The horizontal offset of the shooting position.
*   **`offset.y`**: `0` - The vertical offset of the shooting position.

## Sprite Component

Defines the visual offset of the wand sprite.

```xml
<SpriteComponent 
  image_file="data/items_gfx/wands/wand_0830.png" 
  offset_x="2" 
  offset_y="5" >
</SpriteComponent>
```

*   **`offset_x`**: `2` - The horizontal offset of the sprite.
*   **`offset_y`**: `5` - The vertical offset of the sprite.