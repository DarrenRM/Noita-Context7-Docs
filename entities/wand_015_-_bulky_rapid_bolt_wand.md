---
title: Wand 015 - Bulky Rapid Bolt Wand
category: entities
---

# Wand 015 - Bulky Rapid Bolt Wand

This document details the configuration for a specific wand entity in Noita, identified as `wand_015`. It's designed for AI-assisted modding, highlighting key attributes for understanding and modification.

## Entity Definition

```xml
<Entity 
  _version="1" 
  name="" 
  serialize="1" 
  tags="teleportable_NOT,item,wand" >
  </Entity>
```

*   **`tags`**: `teleportable_NOT`, `item`, `wand` - Indicates this entity is an item, specifically a wand, and cannot be teleported.

## Base Wand Configuration

This wand inherits its core functionality from a base wand template.

```xml
<Base file="data/entities/items/wands/level_01/base_wand_level_1.xml" >
  </Base>
```

## Ability Component

This component defines the wand's magical properties and behavior.

```xml
<AbilityComponent 
  _enabled="1" 
  charge_wait_frames="10" 
  cooldown_frames="0" 
  current_slot_durability="60" 
  entity_count="1" 
  item_recoil_max="1" 
  item_recoil_offset_coeff="1" 
  item_recoil_recovery_speed="15" 
  item_recoil_rotation_coeff="5" 
  mana="170" 
  mana_charge_speed="49" 
  mana_max="170" 
  rotate_hand_amount="0.7" 
  rotate_in_hand="1" 
  rotate_in_hand_amount="1" 
  sprite_file="data/items_gfx/wands/wand_0063.png" 
  ui_name="Bulky Rapid bolt wand" 
  use_gun_script="1" >
  </AbilityComponent>
```

*   **`charge_wait_frames`**: `10` - The number of frames to wait before the wand can be fired again after a full charge.
*   **`mana`**: `170` - The current mana pool of the wand.
*   **`mana_max`**: `170` - The maximum mana the wand can hold.
*   **`mana_charge_speed`**: `49` - How quickly the wand regenerates mana.
*   **`sprite_file`**: `data/items_gfx/wands/wand_0063.png` - The visual sprite for the wand.
*   **`ui_name`**: `Bulky Rapid bolt wand` - The name displayed in the game's UI.
*   **`use_gun_script`**: `1` - Indicates that the wand uses a script for its firing behavior.

### Gun Configuration

Defines the core mechanics of how the wand fires projectiles.

```xml
<gun_config 
  actions_per_round="1" 
  deck_capacity="11" 
  reload_time="53" 
  shuffle_deck_when_empty="1" >
  </gun_config>
```

*   **`actions_per_round`**: `1` - The number of spell actions executed per shot.
*   **`deck_capacity`**: `11` - The maximum number of spell cards the wand can hold in its deck.
*   **`reload_time`**: `53` - The time in frames it takes to reload the wand.
*   **`shuffle_deck_when_empty`**: `1` - The wand's deck will be shuffled when it runs out of cards.

### Gun Action Configuration

Specifies the properties of the projectile fired by the wand.

```xml
<gunaction_config 
  action_mana_drain="10" 
  fire_rate_wait="24" 
  speed_multiplier="0.904531" 
  spread_degrees="1" >
  </gunaction_config>
```

*   **`action_mana_drain`**: `10` - The amount of mana consumed per shot.
*   **`fire_rate_wait`**: `24` - The delay in frames between firing actions within a single round.
*   **`speed_multiplier`**: `0.904531` - A multiplier applied to the projectile's base speed.
*   **`spread_degrees`**: `1` - The angular spread of the projectiles fired.

## Hotspot Component

Defines the point from which projectiles are fired.

```xml
<HotspotComponent 
  _tags="shoot_pos" 
  offset.x="13" 
  offset.y="0" >
  </HotspotComponent>
```

*   **`offset.x`**: `13` - The horizontal offset of the shooting position.
*   **`offset.y`**: `0` - The vertical offset of the shooting position.

## Sprite Component

Defines the visual representation of the wand in the game world.

```xml
<SpriteComponent 
  _enabled="1" 
  image_file="data/items_gfx/wands/wand_0063.png" 
  offset_x="1" 
  offset_y="5" >
  </SpriteComponent>
```

*   **`image_file`**: `data/items_gfx/wands/wand_0063.png` - The sprite image used for the wand.
*   **`offset_x`**: `1` - The horizontal offset of the sprite.
*   **`offset_y`**: `5` - The vertical offset of the sprite.