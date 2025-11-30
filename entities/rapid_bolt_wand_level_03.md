---
title: Rapid Bolt Wand (Level 03)
category: entities
---

# Rapid Bolt Wand (Level 03)

This document describes the configuration for the "Rapid bolt wand," a wand entity in Noita, designed for AI-assisted modding.

## Entity Structure

The wand is built upon several base entity types and incorporates specific components to define its behavior and appearance.

*   **`Base file="data/entities/base_item.xml"`**: Inherits fundamental item properties.
    *   **`SpriteComponent`**: Defines visual aspects, including animations.
        *   `next_rect_animation`: Specifies the animation sequence for the sprite.
    *   **`ItemComponent`**: Handles item-specific interactions.
        *   `play_hover_animation`: Enables a hover animation when the item is interacted with.
    *   **`SimplePhysicsComponent`**: Manages physics, disabled by default (`_enabled="0"`).

*   **`Base file="data/entities/base_wand.xml"`**: Inherits core wand functionalities.

*   **`AbilityComponent`**: Defines the wand's magical capabilities.
    *   **Key Attributes**:
        *   `ui_name`: "Rapid bolt wand" - The display name of the wand.
        *   `sprite_file`: "data/items_gfx/machinegun.xml" - The graphical asset for the wand.
        *   `mana_max`: 300 - The maximum mana capacity of the wand.
        *   `mana_charge_speed`: 80 - The speed at which mana regenerates.
        *   `cooldown_frames`: 0 - No cooldown between shots.
        *   `reload_time_frames`: 0 - No reload time.
        *   `amount_in_inventory`: 1 - The default quantity when found.
        *   `max_amount_in_inventory`: 1 - The maximum quantity that can be held.
        *   `use_gun_script`: 1 - Indicates that a custom script governs the wand's firing behavior.
    *   **`gun_config`**: Configures the wand's firing mechanics.
        *   `deck_capacity`: 8 - The number of spells that can be held in the wand's "deck."
        *   `reload_time`: 18 - The time in frames to reload the deck.
        *   `shuffle_deck_when_empty`: 1 - The spell deck is shuffled when it becomes empty.
        *   `actions_per_round`: 1 - Number of actions performed per firing cycle.
    *   **`gunaction_config`**: Configures actions during firing.
        *   `fire_rate_wait`: 5 - The wait time in frames between firing actions.

*   **`HotspotComponent`**: Defines points of interest on the entity.
    *   `_tags="shoot_pos"`: Marks this hotspot as the firing position.
    *   `offset.x="20"`: Horizontal offset for the firing position.
    *   `offset.y="0"`: Vertical offset for the firing position.

*   **`LuaComponent`**: Executes custom Lua scripts.
    *   `script_source_file`: "data/scripts/gun/procedural/wand_level_03.lua" - The primary script that defines the wand's procedural generation and behavior.
    *   `execute_on_added`: 1 - The script runs when the entity is added to the game.
    *   `remove_after_executed`: 1 - The Lua component is removed after its initial execution.

*   **`ManaReloaderComponent`**: Manages mana regeneration for the wand.
    *   `_tags="enabled_in_world,enabled_in_hand,enabled_in_inventory"`: The component is active in various game states.

## Key Attributes for Modding

When modifying this wand, focus on the following attributes within the `AbilityComponent` and its nested configurations:

| Attribute Name              | Description                                                              | Default Value |
| :-------------------------- | :----------------------------------------------------------------------- | :------------ |
| `ui_name`                   | The name displayed in the game.                                          | Rapid bolt wand |
| `sprite_file`               | Path to the graphical asset for the wand.                                | data/items_gfx/machinegun.xml |
| `mana_max`                  | Maximum mana capacity.                                                   | 300           |
| `mana_charge_speed`         | Speed of mana regeneration.                                              | 80            |
| `cooldown_frames`           | Time in frames between shots (0 means no cooldown).                      | 0             |
| `reload_time_frames`        | Time in frames to reload the wand (0 means no reload).                   | 0             |
| `deck_capacity`             | Number of spells that can be held in the wand's spell deck.              | 8             |
| `reload_time`               | Time in frames to reload the spell deck.                                 | 18            |
| `fire_rate_wait`            | Wait time in frames between firing actions within a single shot.          | 5             |
| `script_source_file`        | Path to the Lua script that defines the wand's procedural generation.    | data/scripts/gun/procedural/wand_level_03.lua |

## Associated Scripts

*   **`data/scripts/gun/procedural/wand_level_03.lua`**: This script is crucial for defining the specific spells and behaviors associated with this "Level 03" wand. Modders should examine this file to understand how spells are selected, combined, and executed.