---
title: Shiny Rapid Bolt Wand
category: entities
---

# Shiny Rapid Bolt Wand

This document details the configuration for the "Shiny Rapid Bolt Wand" in Noita, intended for AI-assisted modding.

## Core Entity Properties

The wand is defined as a hittable entity with serialization enabled.

```xml
<Entity 
  name="" 
  serialize="1" 
  tags="hittable" >
  <Base file="data/entities/base_wand_pickup.xml"></Base>
</Entity>
```

## Ability Component (Wand Functionality)

This component governs the wand's core mechanics, including mana, firing rate, and visual representation.

### Key Attributes:

*   **ui\_name**: "Shiny Rapid bolt wand" - The name displayed in-game.
*   **sprite\_file**: "data/items\_gfx/wands/wand\_0120.png" - The visual sprite for the wand.
*   **mana**: 170 - The total mana capacity of the wand.
*   **mana\_max**: 170 - The maximum mana the wand can hold.
*   **mana\_charge\_speed**: 55 - How quickly mana regenerates.
*   **charge\_wait\_frames**: 10 - Delay between shots.
*   **reload\_time\_frames**: 40 - Time to reload.
*   **item\_recoil\_max**: 1 - Maximum recoil applied.
*   **rotate\_in\_hand**: 1 - Whether the wand rotates in the player's hand.
*   **rotate\_hand\_amount**: 0.7 - The degree of hand rotation.

### Gun Configuration:

*   **deck\_capacity**: 3 - The number of spells the wand can hold in its deck.
*   **reload\_time**: 40 - Specific reload time in frames.

```xml
<AbilityComponent 
  _enabled="1" 
  add_these_child_actions="" 
  amount_in_inventory="1" 
  base_item_file="data/entities/base_item.xml" 
  charge_wait_frames="10" 
  cooldown_frames="0" 
  current_slot_durability="160" 
  drop_as_item_on_death="1" 
  entity_count="1" 
  entity_file="" 
  fast_projectile="0" 
  item_recoil_max="1" 
  item_recoil_offset_coeff="1" 
  item_recoil_recovery_speed="15" 
  item_recoil_rotation_coeff="5" 
  mChargeCount="0" 
  mIsInitialized="1" 
  mana="170" 
  mana_charge_speed="55" 
  mana_max="170" 
  max_amount_in_inventory="1" 
  max_charged_actions="0" 
  never_reload="0" 
  reload_time_frames="40" 
  rotate_hand_amount="0.7" 
  rotate_in_hand="1" 
  rotate_in_hand_amount="1" 
  shooting_reduces_amount_in_inventory="0" 
  slot_consumption_function="_get_gun_slot_durability_default" 
  sprite_file="data/items_gfx/wands/wand_0120.png" 
  swim_propel_amount="0" 
  throw_as_item="0" 
  ui_name="Shiny Rapid bolt wand" 
  use_gun_script="1" >
  <gun_config 
    actions_per_round="1" 
    deck_capacity="3" 
    reload_time="40" 
    shuffle_deck_when_empty="0" >
  </gun_config>
  <gunaction_config 
    action_mana_drain="10" 
    fire_rate_wait="26" 
    speed_multiplier="0.955205" 
    spread_degrees="1" >
  </gunaction_config>
</AbilityComponent>
```

## Item Component (Pickup and Inventory)

This component defines how the wand behaves as an item in the game world and inventory.

### Key Attributes:

*   **is\_pickable**: 1 - Allows the player to pick up the wand.
*   **is\_equipable\_forced**: 0 - Not forced to equip.
*   **is\_stackable**: 0 - Cannot be stacked in inventory.
*   **ui\_description**: "" - No specific in-game description.
*   **ui\_sprite**: "" - Uses the main sprite for UI.
*   **uses\_remaining**: -1 - Indicates infinite uses (as a wand).
*   **play\_hover\_animation**: 1 - Plays a hover animation when in inventory.

```xml
<ItemComponent 
  _enabled="1" 
  _tags="enabled_in_world" 
  camera_max_distance="50" 
  collect_nondefault_actions="0" 
  is_consumable="0" 
  is_equipable_forced="0" 
  is_frozen="0" 
  is_hittable_always="0" 
  is_identified="1" 
  is_pickable="1" 
  is_stackable="0" 
  item_name="" 
  mFramePickedUp="100446" 
  max_child_items="0" 
  next_frame_pickable="0" 
  permanently_attached="0" 
  preferred_inventory="QUICK" 
  remove_default_child_actions_on_death="0" 
  remove_on_death="0" 
  remove_on_death_if_empty="0" 
  ui_description="" 
  ui_sprite="" 
  uses_remaining="-1" 
  play_hover_animation="1"
  play_spinning_animation="0"
  >
</ItemComponent>
```

## Sprite Component (Visuals)

Defines the visual representation of the wand in the game world and when held.

### Key Attributes:

*   **image\_file**: "data/items\_gfx/wands/wand\_0120.png" - The primary image file for the sprite.
*   **offset\_x**: 1 - X-axis offset for the sprite.
*   **offset\_y**: 8 - Y-axis offset for the sprite.
*   **z\_index**: 0.595 - Determines the rendering order.

```xml
<SpriteComponent 
  _enabled="1" 
  _tags="enabled_in_world,item,enabled_in_hand" 
  additive="0" 
  alpha="1" 
  emissive="0" 
  fog_of_war_hole="0" 
  has_special_scale="0" 
  image_file="data/items_gfx/wands/wand_0120.png" 
  is_text_sprite="0" 
  kill_entity_after_finished="0" 
  never_ragdollify_on_death="0" 
  next_rect_animation="" 
  offset_x="1" 
  offset_y="8" 
  rect_animation="" 
  smooth_filtering="0" 
  special_scale_x="1" 
  special_scale_y="1" 
  text="" 
  transform_offset.x="0" 
  transform_offset.y="0" 
  ui_is_parent="0" 
  update_transform="1" 
  update_transform_rotation="1" 
  visible="1" 
  z_index="0.595" >
</SpriteComponent>
```

## Lua Component (Procedural Generation)

This component links the wand to a Lua script responsible for its procedural generation.

*   **script\_source\_file**: "data/scripts/gun/procedural/level\_1\_wand.lua" - The script that defines the wand's properties during generation.

```xml
<LuaComponent 
  _enabled="1" 
  execute_on_added="1"
  remove_after_executed="1"
  script_source_file="data/scripts/gun/procedural/level_1_wand.lua" 
>
</LuaComponent>
```

## Other Components

*   **\_Transform**: Defines the initial position and rotation of the wand in the game world.
*   **AudioLoopComponent**: Handles sound effects associated with the wand.
*   **HitboxComponent**: Defines the collision area of the wand.
*   **HotspotComponent**: Specifies the firing position for the wand.
*   **ItemAlchemyComponent**: Defines alchemy interactions for the wand.
*   **LightComponent**: Controls any light emitted by the wand.
*   **ManaReloaderComponent**: Enables mana regeneration for the wand.
*   **SimplePhysicsComponent**: Basic physics properties for the wand.
*   **SpriteParticleEmitterComponent**: Manages particle effects, likely for visual flair.
*   **VelocityComponent**: Defines the initial velocity and physics for when the wand is thrown or dropped.