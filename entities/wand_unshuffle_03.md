---
title: Wand Unshuffle 03
category: entities
---

# Wand Unshuffle 03

This document describes the `wand_unshuffle_03.xml` entity, which defines a specific type of wand in Noita. This wand is characterized by its "unshuffle" behavior, meaning its spell deck does not shuffle after each cast.

## Key Attributes

### Base Entity Configuration

*   **`Base file="data/entities/base_item.xml"`**: Inherits fundamental item properties.
    *   **`SpriteComponent`**: Defines visual aspects, including animations.
        *   `next_rect_animation="JobAbilityMachinegun"`: Suggests a visual connection to machinegun-like animations.
    *   **`ItemComponent`**: Handles item-specific behaviors.
        *   `play_hover_animation="1"`: Enables a hover animation when the item is interacted with.
    *   **`SimplePhysicsComponent`**: Controls physics, but is disabled (`_enabled="0"`) for this wand.

*   **`Base file="data/entities/base_wand.xml"`**: Inherits core wand functionalities.

### Ability Component (Wand Specifics)

*   **`AbilityComponent`**: Manages the wand's magical abilities and firing mechanics.
    *   `ui_name="Rapid bolt wand"`: The in-game name displayed to the player.
    *   `sprite_file="data/items_gfx/machinegun.xml"`: Specifies the graphical asset for the wand.
    *   `mana_max="300"`: The maximum mana capacity of the wand.
    *   `mana_charge_speed="80"`: How quickly the wand recharges mana.
    *   `cooldown_frames="0"`: No cooldown between shots.
    *   `reload_time_frames="0"`: No reload time between firing sequences.
    *   `use_gun_script="1"`: Indicates that a custom script controls the firing behavior.

#### Gun Configuration

*   **`gun_config`**: Defines parameters for how the wand's spell deck operates.
    *   `actions_per_round="1"`: The number of spells cast per firing action.
    *   `shuffle_deck_when_empty="0"`: **Crucially, this is set to 0, meaning the spell deck does NOT shuffle when empty.** This is the defining characteristic of an "unshuffle" wand.
    *   `reload_time="18"`: The time in frames it takes to reload the spell deck.
    *   `deck_capacity="8"`: The maximum number of spells that can be held in the wand's deck.

#### Gun Action Configuration

*   **`gunaction_config`**: Fine-tunes the firing action.
    *   `fire_rate_wait="5"`: The delay in frames between casting individual spells within a single firing action.

### Other Components

*   **`HotspotComponent`**: Defines the origin point for projectiles.
    *   `offset.x="20"`: The horizontal offset of the shooting position.
    *   `offset.y="0"`: The vertical offset of the shooting position.

*   **`LuaComponent`**: Executes custom Lua scripts.
    *   `script_source_file="data/scripts/gun/procedural/wand_unshuffle_03.lua"`: This is the core script that dictates the wand's unique "unshuffle" behavior and potentially other procedural generation aspects of its spells.
    *   `execute_on_added="1"`: The script runs when the wand is first added to the game.
    *   `remove_after_executed="1"`: The script is removed after its initial execution.

*   **`ManaReloaderComponent`**: Enables mana regeneration for the wand in various states (world, hand, inventory).