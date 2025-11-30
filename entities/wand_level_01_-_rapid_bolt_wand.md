---
title: Wand Level 01 - Rapid Bolt Wand
category: entities
---

# Wand Level 01 - Rapid Bolt Wand

This entity defines a basic wand, specifically a "Rapid Bolt Wand," designed for rapid projectile firing. It inherits core functionality from `base_item.xml` and `base_wand.xml`, with specific configurations for its abilities and appearance.

## Key Components and Attributes

### Base Components

*   **`Base file="data/entities/base_item.xml"`**: Inherits fundamental properties of an item.
    *   **`SpriteComponent`**: Defines the visual appearance and animations.
        *   `next_rect_animation`: Specifies the animation sequence for the sprite.
    *   **`ItemComponent`**: Handles item-specific behaviors.
        *   `play_hover_animation`: Enables a hover animation when the item is interacted with.
    *   **`SimplePhysicsComponent`**: Controls physics interactions.
        *   `_enabled="0"`: Disables physics for this item, likely to prevent it from falling or reacting to physical forces in a standard way.

*   **`Base file="data/entities/base_wand.xml"`**: Inherits core wand mechanics.

### Ability Component

*   **`AbilityComponent`**: Configures the wand's primary function as a weapon.
    *   `amount_in_inventory="1"`: The default quantity of this wand when found.
    *   `cooldown_frames="0"`: No cooldown between firing actions.
    *   `drop_as_item_on_death="1"`: The wand will be dropped as an item if the player dies while holding it.
    *   `entity_count="1"`: The number of entities this ability component affects (typically 1 for a wand).
    *   `entity_file=""`: No specific entity file is directly associated with the projectile.
    *   `fast_projectile="0"`: Projectiles are not inherently fast.
    *   `mana_charge_speed="30"`: The speed at which mana regenerates.
    *   `mana_max="100"`: The maximum mana capacity of the wand.
    *   `max_amount_in_inventory="1"`: Only one of this wand can be held in the inventory.
    *   `reload_time_frames="0"`: No reload time between firing sequences.
    *   `shooting_reduces_amount_in_inventory="0"`: Firing does not consume the wand itself.
    *   `sprite_file="data/items_gfx/machinegun.xml"`: Specifies the graphical asset for the wand's sprite.
    *   `throw_as_item="0"`: The wand cannot be thrown as a usable item.
    *   `ui_name="Rapid bolt wand"`: The name displayed in the user interface.
    *   `use_gun_script="1"`: Indicates that a custom gun script is used for its behavior.

    #### `gun_config`
    *   `actions_per_round="1"`: One action is performed per firing cycle.
    *   `shuffle_deck_when_empty="1"`: The spell deck is shuffled when it becomes empty.
    *   `reload_time="18"`: The time in frames to reload the spell deck.
    *   `deck_capacity="8"`: The maximum number of spells that can be held in the wand's deck.

    #### `gunaction_config`
    *   `fire_rate_wait="5"`: The wait time in frames between consecutive shots.

### Hotspot Component

*   **`HotspotComponent`**: Defines points of interest on the entity, often for targeting or interaction.
    *   `_tags="shoot_pos"`: Tags this hotspot as a firing position.
    *   `offset.x="20"`: Horizontal offset for the shooting position.
    *   `offset.y="0"`: Vertical offset for the shooting position.

### Lua Component

*   **`LuaComponent`**: Executes custom Lua scripts.
    *   `_enabled="1"`: The script is active.
    *   `execute_on_added="1"`: The script runs immediately when the entity is added to the game.
    *   `remove_after_executed="1"`: The Lua component is removed after its initial execution.
    *   `script_source_file="data/scripts/gun/procedural/wand_level_01.lua"`: The path to the Lua script that defines the wand's procedural generation and behavior.

### Mana Reloader Component

*   **`ManaReloaderComponent`**: Manages mana regeneration for the wand.
    *   `_tags="enabled_in_world,enabled_in_hand,enabled_in_inventory"`: The mana reloader is active in all relevant game states.