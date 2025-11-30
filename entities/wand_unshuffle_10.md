---
title: Wand Unshuffle 10
category: entities
---

# Wand Unshuffle 10

This document describes the `wand_unshuffle_10.xml` entity, which defines a specific type of wand in Noita. This wand is characterized by its "unshuffle" behavior, meaning its spell deck is not shuffled after each cast.

## Key Components and Attributes

### Base Entity Configuration

The wand inherits base properties from `base_item.xml` and `base_wand.xml`.

*   **`base_item.xml`**: Provides fundamental item properties.
    *   `SpriteComponent`: Defines visual aspects, including animations.
        *   `next_rect_animation`: Set to "JobAbilityMachinegun", suggesting a visual connection to rapid firing.
    *   `ItemComponent`: Handles item-specific behaviors.
        *   `play_hover_animation`: Set to "1", enabling a hover animation when the item is interacted with.
    *   `SimplePhysicsComponent`: Disabled (`_enabled="0"`), indicating physics are not a primary concern for this item's base behavior.

*   **`base_wand.xml`**: Provides core wand functionalities.

### Ability Component

This component defines the wand's magical capabilities and how it functions as a weapon.

*   **`AbilityComponent`**:
    *   `ui_name`: "Rapid bolt wand" - The name displayed in the game's UI.
    *   `sprite_file`: "data/items_gfx/machinegun.xml" - Specifies the graphical representation of the wand.
    *   `mana_max`: "1000" - The maximum mana capacity of the wand.
    *   `mana_charge_speed`: "200" - How quickly the wand recharges mana.
    *   `drop_as_item_on_death`: "1" - The wand will be dropped as an item if the player dies while holding it.
    *   `use_gun_script`: "1" - Indicates that a custom script is used for gun behavior.

#### `gun_config`

Defines the core mechanics of the wand's spell casting.

*   `actions_per_round`: "1" - The number of spell actions performed per firing cycle.
*   `shuffle_deck_when_empty`: "0" - **Crucially, this is set to "0", meaning the spell deck will NOT be shuffled when it becomes empty.** This is the defining "unshuffle" behavior.
*   `reload_time`: "18" - The time in frames it takes to reload the wand's spell deck.
*   `deck_capacity`: "8" - The maximum number of spells that can be held in the wand's deck.

#### `gunaction_config`

Controls the timing of spell actions.

*   `fire_rate_wait`: "5" - The delay in frames between consecutive spell casts within a single firing action.

### Hotspot Component

Defines the point from which projectiles are fired.

*   **`HotspotComponent`**:
    *   `_tags`: "shoot_pos" - Identifies this as the firing position.
    *   `offset.x`: "20" - The horizontal offset of the firing position.
    *   `offset.y`: "0" - The vertical offset of the firing position.

### Lua Component

This component links the wand entity to a custom Lua script that dictates its unique behavior.

*   **`LuaComponent`**:
    *   `_enabled`: "1" - The Lua script is active.
    *   `execute_on_added`: "1" - The script will execute immediately when the wand is added to the game.
    *   `remove_after_executed`: "1" - The Lua component will be removed after its initial execution.
    *   `script_source_file`: "data/scripts/gun/procedural/wand_unshuffle_10.lua" - The path to the specific Lua script responsible for the wand's "unshuffle" logic and potentially other procedural behaviors.

### Mana Reloader Component

This component manages how the wand recharges mana.

*   **`ManaReloaderComponent`**:
    *   `_tags`: "enabled_in_world,enabled_in_hand,enabled_in_inventory" - The mana reloader is active in all relevant game states.

---