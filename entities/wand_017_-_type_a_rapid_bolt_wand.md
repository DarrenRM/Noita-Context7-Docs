---
title: Wand 017 - Type a Rapid Bolt Wand
category: entities
---

# Wand 017 - Type a Rapid Bolt Wand

This document details the configuration for a specific wand entity in Noita, designed for rapid bolt casting.

## Entity Definition

```xml
<Entity 
  _version="1" 
  name="" 
  serialize="1" 
  tags="teleportable_NOT,item,wand" >
  <Base file="data/entities/items/wands/level_01/base_wand_level_1.xml" >
    </Base>
</Entity>
```

*   **`name`**: The internal name for this entity (currently empty).
*   **`serialize`**: Indicates if the entity should be serialized (saved/loaded).
*   **`tags`**: `teleportable_NOT` prevents teleportation, `item` and `wand` categorize it.
*   **`Base`**: Inherits properties from a generic level 1 wand.

## Ability Component

This component defines the core functionality of the wand.

```xml
<AbilityComponent 
  _enabled="1" 
  add_these_child_actions="" 
  amount_in_inventory="1" 
  base_item_file="data/entities/base_item.xml" 
  charge_wait_frames="10" 
  click_to_use="1" 
  cooldown_frames="0" 
  current_slot_durability="100" 
  drop_as_item_on_death="1" 
  entity_count="1" 
  entity_file="" 
  fast_projectile="0" 
  is_petris_gun="0" 
  item_recoil_max="1" 
  item_recoil_offset_coeff="1" 
  item_recoil_recovery_speed="15" 
  item_recoil_rotation_coeff="5" 
  mChargeCount="0" 
  mIsInitialized="1" 
  mana="190" 
  mana_charge_speed="52" 
  mana_max="190" 
  max_amount_in_inventory="1" 
  max_charged_actions="0" 
  never_reload="0" 
  reload_time_frames="0" 
  rotate_hand_amount="0.7" 
  rotate_in_hand="1" 
  rotate_in_hand_amount="1" 
  shooting_reduces_amount_in_inventory="0" 
  simulate_throw_as_item="0" 
  slot_consumption_function="_get_gun_slot_durability_default" 
  sprite_file="data/items_gfx/wands/wand_1000.png" 
  stat_times_player_has_edited="0" 
  stat_times_player_has_shot="0" 
  swim_propel_amount="0" 
  throw_as_item="0" 
  ui_name="Type a Rapid bolt wand" 
  use_entity_file_as_projectile_info_proxy="0" 
  use_gun_script="1" >
  </AbilityComponent>
```

### Key Attributes:

*   **`charge_wait_frames`**: 10 frames delay between shots.
*   **`click_to_use`**: 1 (true) - can be activated by clicking.
*   **`mana` / `mana_max`**: 190 - the wand's mana pool.
*   **`mana_charge_speed`**: 52 - how quickly mana regenerates.
*   **`rotate_hand_amount`**: 0.7 - influences hand rotation when aiming.
*   **`sprite_file`**: `data/items_gfx/wands/wand_1000.png` - the visual representation of the wand.
*   **`ui_name`**: "Type a Rapid bolt wand" - the name displayed in the game's UI.
*   **`use_gun_script`**: 1 (true) - indicates this wand uses gun-specific scripting.

#### Gun Configuration

```xml
<gun_config 
  actions_per_round="1" 
  deck_capacity="6" 
  reload_time="14" 
  shuffle_deck_when_empty="1" >
</gun_config>
```

*   **`actions_per_round`**: 1 - fires one spell per action.
*   **`deck_capacity`**: 6 - the wand can hold up to 6 spells in its deck.
*   **`reload_time`**: 14 frames - time taken to reload.
*   **`shuffle_deck_when_empty`**: 1 (true) - the spell deck is shuffled when empty.

#### Gun Action Configuration

This section defines the properties of the projectile fired by the wand.

```xml
<gunaction_config 
  action_mana_drain="10" 
  fire_rate_wait="2" 
  speed_multiplier="0.987879" 
  spread_degrees="5" >
</gunaction_config>
```

*   **`action_mana_drain`**: 10 - mana cost per shot.
*   **`fire_rate_wait`**: 2 frames - additional delay between firing actions.
*   **`speed_multiplier`**: 0.987879 - slight reduction in projectile speed.
*   **`spread_degrees`**: 5 - the projectile will spread by 5 degrees.

## Hotspot Component

Defines the point from which projectiles are fired.

```xml
<HotspotComponent 
  _tags="shoot_pos" 
  offset.x="8" 
  offset.y="0" 
  sprite_hotspot_name="" 
  transform_with_scale="1" >
</HotspotComponent>
```

*   **`_tags`**: `shoot_pos` - identifies this as the shooting position.
*   **`offset.x`**: 8 - the x-coordinate offset for the shooting position.
*   **`offset.y`**: 0 - the y-coordinate offset for the shooting position.

## Sprite Component

Defines the visual sprite for the wand.

```xml
<SpriteComponent 
  image_file="data/items_gfx/wands/wand_1000.png" 
  offset_x="2" 
  offset_y="2" 
>
</SpriteComponent>
```

*   **`image_file`**: `data/items_gfx/wands/wand_1000.png` - the sprite asset used.
*   **`offset_x`**: 2 - x-axis offset for the sprite.
*   **`offset_y`**: 2 - y-axis offset for the sprite.