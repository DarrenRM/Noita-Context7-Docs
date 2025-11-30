---
title: Large Rapid Bolt Wand
category: entities
---

# Large Rapid Bolt Wand

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

*   **`tags`**: Identifies the entity as an item and a wand, and prevents it from being teleported.

## Ability Component

This component governs the wand's magical properties and behavior.

```xml
<AbilityComponent 
  _enabled="1" 
  charge_wait_frames="10" 
  cooldown_frames="0" 
  current_slot_durability="120" 
  entity_count="1" 
  is_petris_gun="0" 
  item_recoil_max="1" 
  item_recoil_offset_coeff="1" 
  item_recoil_recovery_speed="15" 
  item_recoil_rotation_coeff="5" 
  mana="220" 
  mana_charge_speed="51" 
  mana_max="220" 
  rotate_hand_amount="0.7" 
  rotate_in_hand="1" 
  rotate_in_hand_amount="1" 
  shooting_reduces_amount_in_inventory="0" 
  slot_consumption_function="_get_gun_slot_durability_default" 
  sprite_file="data/items_gfx/wands/wand_0309.png" 
  ui_name="Large Rapid bolt wand" 
  use_gun_script="1" >
  <!-- ... gun_config, gunaction_config ... -->
</AbilityComponent>
```

### Key Attributes:

*   **`charge_wait_frames`**: 10 frames delay between shots.
*   **`current_slot_durability`**: 120 durability points.
*   **`mana` / `mana_max`**: 220 mana capacity.
*   **`mana_charge_speed`**: 51 mana recharge speed.
*   **`sprite_file`**: `data/items_gfx/wands/wand_0309.png` - the visual representation of the wand.
*   **`ui_name`**: "Large Rapid bolt wand" - the name displayed in the game UI.
*   **`rotate_in_hand`**: `1` - the wand rotates in the player's hand.

### Gun Configuration (`gun_config`)

Defines the wand's deck and reloading behavior.

```xml
<gun_config 
  actions_per_round="1" 
  deck_capacity="5" 
  reload_time="45" 
  shuffle_deck_when_empty="0" >
</gun_config>
```

*   **`actions_per_round`**: `1` - fires one spell per round.
*   **`deck_capacity`**: `5` - can hold up to 5 spells in its deck.
*   **`reload_time`**: `45` frames to reload.

### Gun Action Configuration (`gunaction_config`)

Specifies the properties of the projectile fired by the wand.

```xml
<gunaction_config 
  action_mana_drain="10" 
  fire_rate_wait="4" 
  speed_multiplier="0.969829" 
  spread_degrees="1" >
</gunaction_config>
```

*   **`action_mana_drain`**: `10` mana cost per shot.
*   **`fire_rate_wait`**: `4` frames between firing actions.
*   **`speed_multiplier`**: `0.969829` - projectile speed is slightly reduced.
*   **`spread_degrees`**: `1` degree spread.

## Hotspot Component

Defines the firing position for projectiles.

```xml
<HotspotComponent 
  _tags="shoot_pos" 
  offset.x="8" 
  offset.y="0" >
</HotspotComponent>
```

*   **`offset.x`**: `8` - the horizontal offset of the firing position.
*   **`offset.y`**: `0` - the vertical offset of the firing position.

## Sprite Component

Defines the visual sprite for the wand.

```xml
<SpriteComponent 
  image_file="data/items_gfx/wands/wand_0309.png" 
  offset_x="1" 
  offset_y="3" >
</SpriteComponent>
```

*   **`image_file`**: `data/items_gfx/wands/wand_0309.png` - the sprite image.
*   **`offset_x`**: `1` - horizontal offset for the sprite.
*   **`offset_y`**: `3` - vertical offset for the sprite.