---
title: Wand Level 05 - Rapid Bolt Wand
category: entities
---

# Wand Level 05 - Rapid Bolt Wand

This document describes the `wand_level_05.xml` entity, which defines a "Rapid Bolt Wand" in Noita. This wand is designed for rapid projectile firing.

## Key Attributes

The wand's behavior and appearance are primarily defined by the following components and their attributes:

### Base Components

*   **`Base file="data/entities/base_item.xml"`**: Inherits fundamental item properties.
    *   **`SpriteComponent`**: Defines the visual appearance and animations.
        *   `next_rect_animation`: Specifies the animation sequence for sprite changes.
    *   **`ItemComponent`**: Handles item-specific behaviors.
        *   `play_hover_animation`: Enables a hover animation when the item is interacted with.
    *   **`SimplePhysicsComponent`**: Controls physics interactions.
        *   `_enabled="0"`: Disables physics for this item, likely meaning it doesn't fall or react to physical forces in the same way as other objects.

*   **`Base file="data/entities/base_wand.xml"`**: Inherits core wand functionalities.

### Ability Component

This component defines the wand's magical capabilities.

*   **`AbilityComponent`**:
    *   `ui_name="Rapid bolt wand"`: The display name of the wand in the game.
    *   `sprite_file="data/items_gfx/machinegun.xml"`: Specifies the graphical asset used for the wand's sprite.
    *   `mana_max="500"`: The maximum mana capacity of the wand.
    *   `mana_charge_speed="120"`: How quickly the wand regenerates mana.
    *   `cooldown_frames="0"`: No cooldown between firing actions.
    *   `reload_time_frames="0"`: No reload time between firing actions.
    *   `drop_as_item_on_death="1"`: The wand will be dropped as an item if the player dies while holding it.
    *   `use_gun_script="1"`: Indicates that the wand's firing behavior is controlled by a script.

#### Gun Configuration

*   **`gun_config`**:
    *   `actions_per_round="1"`: The number of actions (projectiles) fired per "round" of activation.
    *   `shuffle_deck_when_empty="1"`: The wand's spell deck will be shuffled when it runs out of spells.
    *   `reload_time="18"`: The time in frames it takes to reload the wand's spell deck.
    *   `deck_capacity="8"`: The maximum number of spells that can be held in the wand's deck.

#### Gun Action Configuration

*   **`gunaction_config`**:
    *   `fire_rate_wait="5"`: The minimum delay in frames between consecutive shots. This is the primary factor for its "rapid" nature.

### Hotspot Component

*   **`HotspotComponent`**: Defines points of interest on the entity.
    *   `_tags="shoot_pos"`: Marks this hotspot as the position from which projectiles are fired.
    *   `offset.x="20"`: The horizontal offset of the shooting position from the wand's center.
    *   `offset.y="0"`: The vertical offset of the shooting position from the wand's center.

### Lua Component

*   **`LuaComponent`**: Executes Lua scripts.
    *   `script_source_file="data/scripts/gun/procedural/wand_level_05.lua"`: The specific Lua script that governs the wand's procedural generation and firing logic.
    *   `execute_on_added="1"`: The script runs when the entity is first added to the game.
    *   `remove_after_executed="1"`: The script is removed after its initial execution.

### Mana Reloader Component

*   **`ManaReloaderComponent`**: Manages mana regeneration.
    *   `_tags="enabled_in_world,enabled_in_hand,enabled_in_inventory"`: This component is active in all states: in the world, in hand, and in inventory.