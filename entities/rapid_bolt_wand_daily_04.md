---
title: Rapid Bolt Wand (Daily 04)
category: entities
---

# Rapid Bolt Wand (Daily 04)

This entity defines a specific wand item in Noita, designated for daily challenges. It's designed to be a rapid-firing weapon with a focus on projectile speed and a consistent firing pattern.

## Key Components and Attributes

### Base Item and Wand Configuration

*   **`Base file="data/entities/base_item.xml"`**: Inherits fundamental properties of a player-collectible item.
    *   **`SpriteComponent`**: Defines the visual appearance and animations. `next_rect_animation="JobAbilityMachinegun"` suggests a specific animation set related to rapid firing.
    *   **`ItemComponent`**: Handles item interactions. `play_hover_animation="1"` and `has_been_picked_by_player="1"` are standard for player-usable items.
    *   **`SimplePhysicsComponent _enabled="0"`**: Physics are likely handled by the wand mechanics rather than standard item physics.
*   **`Base file="data/entities/base_wand.xml"`**: Inherits core wand functionalities.

### Ability Component (Wand Mechanics)

This component dictates the wand's firing behavior and resource management.

*   **`amount_in_inventory="1"`**: The wand starts with one charge.
*   **`cooldown_frames="0"`**: No inherent cooldown between firing actions.
*   **`drop_as_item_on_death="1"`**: The wand will be dropped if the player dies.
*   **`mana_max="200"`**: The maximum mana capacity of the wand.
*   **`max_amount_in_inventory="1"`**: Only one of this specific wand can be held.
*   **`reload_time_frames="0"`**: No automatic reload time.
*   **`sprite_file="data/items_gfx/machinegun.xml"`**: Specifies the visual asset for the wand itself.
*   **`ui_name="Rapid bolt wand"`**: The name displayed in the game's UI.
*   **`use_gun_script="1"`**: Indicates that a custom Lua script controls the firing behavior.

#### Gun Configuration (`gun_config`)

*   **`actions_per_round="1"`**: Fires one projectile per action.
*   **`shuffle_deck_when_empty="1"`**: If the spell deck is empty, it will be reshuffled.
*   **`reload_time="18"`**: The time in frames to reload the spell deck.
*   **`deck_capacity="8"`**: The wand can hold up to 8 spells in its deck.

#### Gun Action Configuration (`gunaction_config`)

*   **`fire_rate_wait="5"`**: The minimum delay in frames between consecutive shots. This is a key attribute for its rapid-firing nature.

### Hotspot Component

*   **`_tags="shoot_pos"`**: Marks this as the point from which projectiles are fired.
*   **`offset.x="20"`**: The firing position is offset 20 units to the right of the wand's center.

### Lua Component

*   **`script_source_file="data/scripts/gun/procedural/wand_daily_04.lua"`**: This is the core script that defines the unique behavior of this wand, likely handling spell selection, projectile properties, and firing logic.
*   **`execute_on_added="1"`**: The script runs when the wand is added to the game.
*   **`remove_after_executed="1"`**: The script is removed after its initial execution.

### Mana Reloader Component

*   **`_tags="enabled_in_world,enabled_in_hand,enabled_in_inventory"`**: This component ensures the wand's mana recharges when it's in the world, in the player's hand, or in the inventory.