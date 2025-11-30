---
title: Wand Good 3
category: entities
---

# Wand Good 3

This document details the configuration for `wand_good_3`, a wand entity in Noita, intended for AI-assisted modding.

## Entity Definition

The core entity definition for `wand_good_3`.

```xml
<Entity tags="wand,wand_good">
    <!-- Component details follow -->
</Entity>
```

## AbilityComponent

This component governs the wand's magical capabilities and behavior.

### Key Attributes:

*   **`mana_max`**: `100` - The maximum mana capacity of the wand.
*   **`mana_charge_speed`**: `30` - The speed at which mana regenerates.
*   **`cooldown_frames`**: `0` - No cooldown between firing.
*   **`reload_time_frames`**: `0` - No reload time between shots.
*   **`drop_as_item_on_death`**: `1` - The wand will drop as an item when the player dies.
*   **`sprite_file`**: `data/items_gfx/wands/custom/good_03.xml` - Specifies the visual sprite for the wand.
*   **`ui_name`**: `wand_good_3` - The internal name used for UI elements.
*   **`use_gun_script`**: `1` - Indicates that this wand uses a gun script for its firing mechanics.

### `gun_config`

Defines the behavior of the wand's "gun" mechanics.

*   **`deck_capacity`**: `3` - The number of spells that can be held in the wand's "deck".
*   **`reload_time`**: `24` - The time in frames it takes to reload the wand's deck.
*   **`shuffle_deck_when_empty`**: `0` - The deck does not shuffle when empty.

### `gunaction_config`

Configures actions related to firing the wand.

*   **`fire_rate_wait`**: `10` - The delay in frames between consecutive shots.

```xml
<AbilityComponent
    amount_in_inventory="1"
    cooldown_frames="0"
    drop_as_item_on_death="1"
    entity_count="1"
    entity_file=""
    fast_projectile="0"
    mana_charge_speed="30"
    mana_max="100"
    max_amount_in_inventory="1"
    reload_time_frames="0"
    shooting_reduces_amount_in_inventory="0"
    sprite_file="data/items_gfx/wands/custom/good_03.xml"
    swim_propel_amount="0"
    throw_as_item="0"
    ui_name="wand_good_3"
    use_gun_script="1"
    >
    <gun_config
        shuffle_deck_when_empty="0"
        reload_time="24"
        deck_capacity="3" >
    </gun_config>
    <gunaction_config
        fire_rate_wait="10" >
    </gunaction_config>
</AbilityComponent>
```

## HotspotComponent

Defines the point from which projectiles are fired.

*   **`offset.x`**: `15` - Horizontal offset from the wand's center.
*   **`offset.y`**: `-0.5` - Vertical offset from the wand's center.

```xml
<HotspotComponent
    _tags="shoot_pos"
    offset.x="15"
    offset.y="-0.5" >
</HotspotComponent>
```

## Base Item Components

These components define the wand as a general item within the game.

### `ItemComponent`

Basic item properties.

*   **`item_name`**: `wand_good_3` - The internal name of the item.
*   **`play_hover_animation`**: `1` - Enables a hover animation when the item is in the inventory or world.

### `SpriteComponent`

Visual representation of the wand.

*   **`image_file`**: `data/items_gfx/wands/custom/good_03.xml` - The sprite asset.
*   **`z_index`**: `-1.5` - Controls the rendering layer.

```xml
<Base file="data/entities/base_item.xml" >
    <ItemComponent
        item_name="wand_good_3"
        play_hover_animation="1"
        >
    </ItemComponent>

    <SpriteComponent
        _tags="item,enabled_in_world,enabled_in_hand"
        alpha="1"
        image_file="data/items_gfx/wands/custom/good_03.xml"
        next_rect_animation="default"
        rect_animation="default"
        z_index="-1.5" >
    </SpriteComponent>

    <SimplePhysicsComponent
        _enabled="0">
    </SimplePhysicsComponent>
</Base>
```

## Lua Components

These components enable custom scripting for the wand.

### `LuaComponent` (Primary Script)

Executes the main wand logic.

*   **`script_source_file`**: `data/entities/items/wands/wand_good/wand_good_3.lua` - The primary Lua script file for this wand.
*   **`execute_on_added`**: `1` - The script runs when the entity is added to the game.
*   **`remove_after_executed`**: `1` - The script component is removed after execution.

```xml
<LuaComponent
    _enabled="1"
    execute_on_added="1"
    remove_after_executed="1"
    script_source_file="data/entities/items/wands/wand_good/wand_good_3.lua"
>
</LuaComponent>
```

### `LuaComponent` (Pickup Script)

Handles logic when the wand is picked up.

*   **`script_item_picked_up`**: `data/entities/items/wands/wand_good/wand_pickup.lua` - The Lua script executed when the item is picked up.
*   **`remove_after_executed`**: `1` - The script component is removed after execution.

```xml
<LuaComponent
    script_item_picked_up="data/entities/items/wands/wand_good/wand_pickup.lua"
    remove_after_executed="1"
    >
</LuaComponent>
```

## ManaReloaderComponent

This component allows the wand to passively regenerate mana.

```xml
<ManaReloaderComponent
    _tags="enabled_in_world,enabled_in_hand,enabled_in_inventory" >
</ManaReloaderComponent>
```