---
title: Wand Level 01 Better
category: entities
---

---

# Wand Level 01 Better

This document describes the configuration for a basic wand entity in Noita, specifically designed for AI-assisted modding. It focuses on the key attributes that define its behavior and appearance.

## Base Entity Configuration

The wand inherits its fundamental properties from `base_item.xml` and `base_wand.xml`.

### `base_item.xml` Overrides

*   **`SpriteComponent`**:
    *   `next_rect_animation`: Specifies the animation sequence for the sprite, set to "JobAbilityMachinegun".
*   **`ItemComponent`**:
    *   `play_hover_animation`: Enables a hover animation when the item is interacted with.
*   **`SimplePhysicsComponent`**:
    *   `_enabled`: Disabled by default, indicating it doesn't have independent physics.

### `base_wand.xml` Inheritance

This base file provides the core wand functionality, which is then customized by the `AbilityComponent`.

## `AbilityComponent` - Wand Properties

This component defines the specific characteristics of the "Rapid bolt wand".

*   **Inventory & Spawning**:
    *   `amount_in_inventory`: Defaults to 1.
    *   `max_amount_in_inventory`: Maximum stack size in inventory, set to 1.
    *   `drop_as_item_on_death`: If true, the wand drops as an item when the player dies.
    *   `throw_as_item`: If true, the wand can be thrown as an item.
*   **Mana & Reloading**:
    *   `mana_max`: Maximum mana capacity, set to 100.
    *   `mana_charge_speed`: Speed at which mana recharges, set to 30.
    *   `reload_time_frames`: Time in frames to reload the wand, set to 0 (instant reload).
*   **Shooting Mechanics**:
    *   `cooldown_frames`: Cooldown between shots in frames, set to 0.
    *   `shooting_reduces_amount_in_inventory`: If true, shooting consumes an inventory item.
    *   `use_gun_script`: Enables the use of a custom gun script.
*   **Visuals**:
    *   `sprite_file`: Path to the sprite definition for the wand's visual representation ("data/items_gfx/machinegun.xml").
*   **UI**:
    *   `ui_name`: The name displayed in the game's UI, "Rapid bolt wand".

### `gun_config`

Configures the wand's deck and firing pattern.

*   `actions_per_round`: Number of spells cast per "round" of firing, set to 1.
*   `shuffle_deck_when_empty`: If true, the spell deck is shuffled when it becomes empty.
*   `reload_time`: Time in frames to reload the spell deck, set to 18.
*   `deck_capacity`: Maximum number of spells the wand can hold, set to 8.

### `gunaction_config`

Configures the timing of firing actions.

*   `fire_rate_wait`: Delay in frames between consecutive firing actions, set to 5.

## `HotspotComponent`

Defines the origin point for projectiles.

*   `_tags`: Tagged as "shoot_pos", indicating its purpose.
*   `offset.x`: Horizontal offset from the wand's center, set to 20.
*   `offset.y`: Vertical offset from the wand's center, set to 0.

## `LuaComponent`

Attaches a Lua script to the wand for custom behavior.

*   `_enabled`: Script is enabled.
*   `execute_on_added`: The script runs immediately when the entity is added.
*   `remove_after_executed`: The script is removed after it has executed once.
*   `script_source_file`: Path to the Lua script file ("data/scripts/gun/procedural/wand_level_01_better.lua").

## `ManaReloaderComponent`

Enables mana regeneration for the wand.

*   `_tags`: The component is enabled in various game states: "enabled_in_world", "enabled_in_hand", "enabled_in_inventory".