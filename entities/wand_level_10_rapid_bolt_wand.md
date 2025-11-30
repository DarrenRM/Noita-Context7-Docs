---
title: Wand Level 10 (Rapid Bolt Wand)
category: entities
---

---

# Wand Level 10 (Rapid Bolt Wand)

This document describes the configuration for a Level 10 Wand in Noita, specifically the "Rapid bolt wand". It's designed for rapid projectile firing.

## Core Components

The wand is built upon base entity and wand configurations, with specific enhancements for its unique properties.

### Base Entity and Wand

*   **`Base file="data/entities/base_item.xml"`**: Inherits fundamental item properties.
    *   **`SpriteComponent`**: Defines visual aspects, including animations.
        *   `next_rect_animation="JobAbilityMachinegun"`: Specifies the animation set for the wand's sprite.
    *   **`ItemComponent`**: Handles item-specific behaviors.
        *   `play_hover_animation="1"`: Enables a hover animation when the item is interacted with.
    *   **`SimplePhysicsComponent`**: Disabled (`_enabled="0"`), indicating physics are not a primary concern for this item's base behavior.
*   **`Base file="data/entities/base_wand.xml"`**: Inherits core wand functionalities.

### Ability Component (Wand Specifics)

This component defines the wand's firing mechanics and resource management.

*   **`AbilityComponent`**:
    *   `ui_name="Rapid bolt wand"`: The display name of the wand in the game.
    *   `sprite_file="data/items_gfx/machinegun.xml"`: The graphical asset used for the wand.
    *   `mana_max="1000"`: The maximum mana capacity of the wand.
    *   `mana_charge_speed="250"`: How quickly the wand regenerates mana.
    *   `cooldown_frames="0"`: No inherent cooldown between firing actions.
    *   `reload_time_frames="0"`: No inherent reload time between firing actions.
    *   `drop_as_item_on_death="1"`: The wand will be dropped as an item if the player dies.
    *   `use_gun_script="1"`: Indicates that a custom script is used for firing behavior.

#### Gun Configuration

*   **`gun_config`**:
    *   `deck_capacity="8"`: The number of spells that can be held in the wand's spell deck.
    *   `reload_time="18"`: The time in frames it takes to reload the spell deck.
    *   `shuffle_deck_when_empty="1"`: The spell deck will be shuffled when it becomes empty.
    *   `actions_per_round="1"`: One spell action is performed per firing round.

#### Gun Action Configuration

*   **`gunaction_config`**:
    *   `fire_rate_wait="5"`: The minimum delay in frames between consecutive spell casts. This is crucial for the "rapid" nature of the wand.

### Hotspot Component

*   **`HotspotComponent`**: Defines points of interest on the entity.
    *   `_tags="shoot_pos"`: Marks this hotspot as the firing origin.
    *   `offset.x="20"`: The horizontal offset of the firing position from the wand's center.
    *   `offset.y="0"`: The vertical offset of the firing position from the wand's center.

### Lua Component

*   **`LuaComponent`**: Executes custom Lua scripts.
    *   `script_source_file="data/scripts/gun/procedural/wand_level_10.lua"`: The primary script that governs the wand's procedural generation and firing logic.
    *   `execute_on_added="1"`: The script runs when the entity is first added to the game.
    *   `remove_after_executed="1"`: The script is removed after its initial execution.

### Mana Reloader Component

*   **`ManaReloaderComponent`**: Manages mana regeneration.
    *   `_tags="enabled_in_world,enabled_in_hand,enabled_in_inventory"`: The mana reloader is active in all relevant game states.