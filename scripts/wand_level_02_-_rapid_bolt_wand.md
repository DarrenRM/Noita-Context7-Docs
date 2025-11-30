---
title: Wand Level 02 - Rapid Bolt Wand
category: scripts
---

# Wand Level 02 - Rapid Bolt Wand

This document describes the configuration for a specific wand entity in Noita, referred to as "Rapid bolt wand". It leverages base wand and item components, with a custom Lua script for its unique behavior.

## Key Components and Attributes

### Base Entity Configuration

The wand inherits from `base_item.xml` and `base_wand.xml`.

*   **`SpriteComponent`**: Defines the visual appearance and animations.
    *   `next_rect_animation`: Specifies the animation sequence for sprite changes.
*   **`ItemComponent`**: Handles item-specific behaviors.
    *   `play_hover_animation`: Enables a hover animation when the item is interacted with.
*   **`SimplePhysicsComponent`**: Controls physics interactions.
    *   `_enabled="0"`: This component is disabled by default.

### Ability Component (Wand Functionality)

This component defines the core mechanics of the wand.

*   **`ui_name`**: "Rapid bolt wand" - The name displayed in the game.
*   **`sprite_file`**: "data/items_gfx/machinegun.xml" - Specifies the graphical asset for the wand.
*   **`mana_max`**: 200 - The maximum mana capacity of the wand.
*   **`mana_charge_speed`**: 60 - The speed at which mana regenerates.
*   **`max_amount_in_inventory`**: 1 - Only one of this wand can be held at a time.
*   **`drop_as_item_on_death`**: 1 - The wand will be dropped as an item when the player dies.
*   **`use_gun_script`**: 1 - Indicates that a custom script controls the wand's firing behavior.

#### `gun_config`

Defines the configuration for the wand's "gun" mechanics.

*   **`actions_per_round`**: 1 - The number of actions performed per firing cycle.
*   **`deck_capacity`**: 8 - The maximum number of spells that can be held in the wand's "deck".
*   **`reload_time`**: 18 - The time in frames it takes to reload the wand.
*   **`shuffle_deck_when_empty`**: 1 - The spell deck is shuffled when it becomes empty.

#### `gunaction_config`

Configures the actions taken when firing the wand.

*   **`fire_rate_wait`**: 5 - The delay in frames between consecutive shots.

### Hotspot Component

Defines a point of interest on the entity, typically for aiming or firing.

*   **`_tags`**: "shoot_pos" - Identifies this as the firing position.
*   **`offset.x`**: 20 - Horizontal offset for the firing position.
*   **`offset.y`**: 0 - Vertical offset for the firing position.

### Lua Component

This component executes a custom Lua script to define the wand's unique behavior.

*   **`script_source_file`**: "data/scripts/gun/procedural/wand_level_02.lua" - The path to the Lua script file.
*   **`execute_on_added`**: 1 - The script executes immediately when the entity is added.
*   **`remove_after_executed`**: 1 - The Lua component is removed after its script has executed.

### Mana Reloader Component

This component handles mana regeneration for the wand.

*   **`_tags`**: "enabled_in_world,enabled_in_hand,enabled_in_inventory" - The component is active in various game states.