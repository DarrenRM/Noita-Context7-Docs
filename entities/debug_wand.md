---
title: Debug Wand
category: entities
---

---

# Debug Wand

This document describes the `wand_debug.xml` entity, which represents a debug wand in Noita. It's designed for testing and development purposes.

## Key Attributes

The `wand_debug.xml` entity inherits from `base_item.xml` and `base_wand.xml`, incorporating specific components for its functionality.

### Base Item Components

*   **SpriteComponent**: Defines the visual appearance and animations.
    *   `next_rect_animation`: Specifies the animation to use.
*   **ItemComponent**: Handles item-specific behaviors.
    *   `play_hover_animation`: Enables a hover animation when the item is interacted with.
*   **SimplePhysicsComponent**: Manages physics properties.
    *   `_enabled="0"`: This component is disabled by default.

### AbilityComponent (Wand Functionality)

This component defines the core properties of the wand.

*   `ui_name`: "Rapid bolt wand" - The name displayed in the game's UI.
*   `sprite_file`: `data/items_gfx/machinegun.xml` - Specifies the graphical asset for the wand.
*   `mana_max`: `1000` - The maximum mana capacity of the wand.
*   `mana_charge_speed`: `200` - How quickly the wand recharges mana.
*   `cooldown_frames`: `0` - No cooldown between shots.
*   `reload_time_frames`: `0` - No reload time.
*   `amount_in_inventory`: `1` - How many of this wand can be held.
*   `max_amount_in_inventory`: `1` - Maximum stack size.
*   `drop_as_item_on_death`: `1` - The wand will drop as an item when the player dies.
*   `use_gun_script`: `1` - Indicates that the wand uses a script for its firing behavior.

#### `gun_config`

*   `actions_per_round`: `1` - Number of actions per firing cycle.
*   `deck_capacity`: `8` - The number of spells that can be held in the wand's "deck".
*   `shuffle_deck_when_empty`: `0` - The spell deck does not shuffle when empty.
*   `reload_time`: `18` - The time in frames to reload the spell deck.

#### `gunaction_config`

*   `fire_rate_wait`: `5` - The delay in frames between firing actions.

### HotspotComponent

*   `_tags`: `shoot_pos` - Marks this as a position for shooting projectiles.
*   `offset.x`: `20` - Horizontal offset for the shooting position.
*   `offset.y`: `0` - Vertical offset for the shooting position.

### LuaComponent

*   `_enabled`: `1` - The Lua script is enabled.
*   `execute_on_added`: `1` - The script will execute when the entity is added.
*   `remove_after_executed`: `1` - The Lua component will be removed after execution.
*   `script_source_file`: `data/entities/_debug/wand_debug.lua` - The path to the associated Lua script.

### ManaReloaderComponent

*   `_tags`: `enabled_in_world,enabled_in_hand,enabled_in_inventory` - The mana reloader is active in various game states.