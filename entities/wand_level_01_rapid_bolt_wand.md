---
title: Wand Level 01 (Rapid Bolt Wand)
category: entities
---

# Wand Level 01 (Rapid Bolt Wand)

This document describes the `wand_level_01_p.xml` entity, which defines a basic wand with rapid firing capabilities.

## Core Components

This wand is built upon several base entity files and incorporates specific components to define its behavior and appearance.

### Base Files

*   **`data/entities/base_wand_physics.xml`**: Provides fundamental physics and sprite properties for wands.
    *   `SpriteComponent`: Configures sprite animations, specifically `next_rect_animation="JobAbilityMachinegun"`.
    *   `ItemComponent`: Enables hover animations when the item is interacted with (`play_hover_animation="1"`).
*   **`data/entities/base_wand.xml`**: Inherits general wand functionalities.

### Ability Component

This is the primary component defining the wand's magical properties and firing mechanics.

*   **`AbilityComponent`**:
    *   `ui_name`: "Rapid bolt wand" - The name displayed in-game.
    *   `sprite_file`: `data/items_gfx/machinegun.xml` - Specifies the visual representation of the wand.
    *   `mana_max`: `100` - The maximum mana capacity of the wand.
    *   `mana_charge_speed`: `30` - How quickly mana regenerates.
    *   `cooldown_frames`: `0` - No cooldown between firing actions.
    *   `reload_time_frames`: `0` - No reload time after emptying the deck.
    *   `amount_in_inventory`: `1` - The default quantity when found.
    *   `max_amount_in_inventory`: `1` - Cannot stack this wand.
    *   `drop_as_item_on_death`: `1` - The wand will drop when the player dies.
    *   `use_gun_script`: `1` - Indicates that a specific gun script will be used.

#### Gun Configuration

*   **`gun_config`**:
    *   `actions_per_round`: `1` - Fires one projectile per action.
    *   `deck_capacity`: `8` - The wand can hold up to 8 spells in its "deck".
    *   `shuffle_deck_when_empty`: `1` - The spell deck is shuffled when it becomes empty.
    *   `reload_time`: `18` - The time in frames to reload the deck.

*   **`gunaction_config`**:
    *   `fire_rate_wait`: `5` - The delay in frames between consecutive shots.

### Hotspot Component

*   **`HotspotComponent`**:
    *   `_tags`: `shoot_pos` - Marks this as the firing origin.
    *   `offset.x`: `20` - The horizontal offset of the firing position.
    *   `offset.y`: `0` - The vertical offset of the firing position.

### Lua Component

*   **`LuaComponent`**:
    *   `script_source_file`: `data/scripts/gun/procedural/wand_level_01.lua` - Links to the script that procedurally generates the wand's spells.
    *   `execute_on_added`: `1` - The script runs when the wand is first added.
    *   `remove_after_executed`: `1` - The script is removed after its initial execution.

### Mana Reloader Component

*   **`ManaReloaderComponent`**:
    *   `_tags`: `enabled_in_world,enabled_in_hand,enabled_in_inventory` - Ensures mana regeneration is active in various game states.