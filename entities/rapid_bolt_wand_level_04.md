---
title: Rapid Bolt Wand (Level 04)
category: entities
---

# Rapid Bolt Wand (Level 04)

This document details the configuration for the "Rapid bolt wand," a level 04 wand entity in Noita, designed for AI-assisted modding.

## Entity Structure

The wand is composed of several base entities and specific components that define its behavior and appearance.

### Base Entities

*   **`data/entities/base_item.xml`**: Provides fundamental item properties like sprite rendering and hover animations.
*   **`data/entities/base_wand.xml`**: Inherits core wand functionalities.

### Key Components

*   **`SpriteComponent`**:
    *   `next_rect_animation`: "JobAbilityMachinegun" - Defines the animation sequence for the wand's sprite.

*   **`ItemComponent`**:
    *   `play_hover_animation`: "1" - Enables a hover animation when the item is interacted with.

*   **`AbilityComponent`**: This is the primary component defining the wand's magical capabilities.
    *   `ui_name`: "Rapid bolt wand" - The in-game name displayed to the player.
    *   `sprite_file`: "data/items_gfx/machinegun.xml" - Specifies the graphical asset for the wand.
    *   `mana_max`: "400" - The maximum mana capacity of the wand.
    *   `mana_charge_speed`: "100" - How quickly the wand recharges mana.
    *   `drop_as_item_on_death`: "1" - The wand will be dropped as an item if the player dies while holding it.
    *   `use_gun_script`: "1" - Indicates that a custom script governs the wand's firing behavior.

    #### `gun_config`
    *   `reload_time`: "18" - The base time in frames to reload the wand.
    *   `deck_capacity`: "8" - The number of spells that can be held in the wand's spell deck.
    *   `shuffle_deck_when_empty`: "1" - The spell deck will be shuffled when it becomes empty.

    #### `gunaction_config`
    *   `fire_rate_wait`: "5" - The minimum delay in frames between consecutive shots.

*   **`HotspotComponent`**:
    *   `_tags`: "shoot_pos" - Marks this component as the origin point for projectiles.
    *   `offset.x`: "20" - The horizontal offset of the shooting position from the wand's center.

*   **`LuaComponent`**:
    *   `script_source_file`: "data/scripts/gun/procedural/wand_level_04_better.lua" - The path to the Lua script that controls the wand's procedural generation and firing logic.
    *   `execute_on_added`: "1" - The script will execute automatically when the wand is added to the game.
    *   `remove_after_executed`: "1" - The Lua component will be removed after its initial execution.

*   **`ManaReloaderComponent`**:
    *   `_tags`: "enabled_in_world,enabled_in_hand,enabled_in_inventory" - Ensures the mana reloader is active in various game states.