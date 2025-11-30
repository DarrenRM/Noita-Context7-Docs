---
title: Wand Level 05 Better
category: entities
---

# Wand Level 05 Better

This document describes the configuration for a "Rapid bolt wand" entity in Noita, designed for AI-assisted modding. It inherits base wand functionality and customizes its firing behavior and appearance.

## Core Components

### Base Item and Wand Configuration

*   **`Base file="data/entities/base_item.xml"`**: Inherits fundamental item properties.
    *   **`SpriteComponent`**: Defines the visual animation for the wand.
        *   `next_rect_animation="JobAbilityMachinegun"`: Specifies the animation sequence.
    *   **`ItemComponent`**: Controls item interaction.
        *   `play_hover_animation="1"`: Enables a hover animation when the item is interacted with.
    *   **`SimplePhysicsComponent`**: Disabled (`_enabled="0"`) as physics are handled by the wand system.
*   **`Base file="data/entities/base_wand.xml"`**: Inherits all standard wand behaviors.

### Ability Component (Wand Specifics)

This component defines the core mechanics of the wand's firing and mana management.

*   **`AbilityComponent`**:
    *   `ui_name="Rapid bolt wand"`: The in-game name displayed to the player.
    *   `sprite_file="data/items_gfx/machinegun.xml"`: The visual asset used for the wand's sprite.
    *   `mana_max="500"`: The maximum mana capacity of the wand.
    *   `mana_charge_speed="120"`: The speed at which mana regenerates.
    *   `drop_as_item_on_death="1"`: The wand will be dropped as an item if the player dies.
    *   `amount_in_inventory="1"`: The default quantity when found.
    *   `max_amount_in_inventory="1"`: The maximum quantity that can be held.
    *   `use_gun_script="1"`: Indicates that a custom script controls the gun's behavior.

#### Gun Configuration

*   **`gun_config`**:
    *   `deck_capacity="8"`: The number of spells that can be held in the wand's spell deck.
    *   `reload_time="18"`: The time in frames it takes to reload the wand after firing.
    *   `shuffle_deck_when_empty="1"`: The spell deck will be shuffled when it becomes empty.
*   **`gunaction_config`**:
    *   `fire_rate_wait="5"`: The minimum delay in frames between firing actions.

### Hotspot Component

*   **`HotspotComponent`**: Defines the origin point for projectiles.
    *   `_tags="shoot_pos"`: Identifies this as the shooting position.
    *   `offset.x="20"`: The horizontal offset of the shooting position.
    *   `offset.y="0"`: The vertical offset of the shooting position.

### Lua Component

*   **`LuaComponent`**: Executes custom Lua scripts for advanced functionality.
    *   `script_source_file="data/scripts/gun/procedural/wand_level_05_better.lua"`: The path to the custom script that defines the wand's unique behavior, likely related to its "rapid bolt" nature.
    *   `execute_on_added="1"`: The script runs when the entity is first added.
    *   `remove_after_executed="1"`: The Lua component is removed after its initial execution.

### Mana Reloader Component

*   **`ManaReloaderComponent`**: Enables mana regeneration for the wand.
    *   `_tags="enabled_in_world,enabled_in_hand,enabled_in_inventory"`: The component is active in all relevant game states.