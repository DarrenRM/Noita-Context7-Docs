---
title: Rapid Bolt Wand (Daily 05)
category: entities
---

# Rapid Bolt Wand (Daily 05)

This entity defines a specific wand item in Noita, characterized by its rapid firing capability and a unique procedural generation script.

## Key Attributes

This wand is designed to be a fast-firing weapon with a focus on projectile speed and a consistent firing pattern.

### Base Item and Wand Properties

*   **`base_item.xml`**: Inherits fundamental item properties.
    *   `SpriteComponent`: Defines the visual appearance and animations.
        *   `next_rect_animation`: "JobAbilityMachinegun" suggests a specific animation set.
    *   `ItemComponent`: Handles item interaction.
        *   `play_hover_animation`: "1" enables hover animations when the item is interacted with.
        *   `has_been_picked_by_player`: "1" indicates it's intended to be picked up by the player.
    *   `SimplePhysicsComponent`: Disabled (`_enabled="0"`) as physics are handled by the wand mechanics.
*   **`base_wand.xml`**: Inherits core wand functionality.

### Ability Component (Wand Mechanics)

This component governs the wand's firing behavior and resource management.

*   `amount_in_inventory`: "1" - The wand is typically found as a single unit.
*   `cooldown_frames`: "0" - No inherent cooldown between firing actions.
*   `drop_as_item_on_death`: "1" - The wand will be dropped as an item if the player dies.
*   `entity_count`: "1" - Refers to the number of entities this wand represents.
*   `mana_charge_speed`: "60" - How quickly mana regenerates.
*   `mana_max`: "200" - The maximum mana capacity of the wand.
*   `max_amount_in_inventory`: "1" - Only one of this specific wand can be held.
*   `reload_time_frames`: "0" - No inherent reload time.
*   `shooting_reduces_amount_in_inventory`: "0" - Firing does not consume the wand itself.
*   `sprite_file`: "data/items_gfx/machinegun.xml" - Specifies the visual asset for the wand.
*   `ui_name`: "Rapid bolt wand" - The name displayed in the game's UI.
*   `use_gun_script`: "1" - Indicates that a custom script controls the gun's behavior.

#### Gun Configuration

*   `gun_config`:
    *   `actions_per_round`: "1" - Performs one action per firing cycle.
    *   `shuffle_deck_when_empty`: "1" - The spell deck will be shuffled when it runs out of spells.
    *   `reload_time`: "18" - The time in frames to reload the spell deck.
    *   `deck_capacity`: "8" - The maximum number of spells that can be held in the wand's deck.
*   `gunaction_config`:
    *   `fire_rate_wait`: "5" - The delay in frames between consecutive shots.

### Hotspot Component

*   `_tags`: "shoot_pos" - Marks this as the firing origin.
*   `offset.x`: "20" - The horizontal offset of the firing position.
*   `offset.y`: "0" - The vertical offset of the firing position.

### Lua Component

*   `_enabled`: "1" - The Lua script is active.
*   `execute_on_added`: "1" - The script runs immediately when the wand is added.
*   `remove_after_executed`: "1" - The script is removed after its initial execution.
*   `script_source_file`: "data/scripts/gun/procedural/wand_daily_05.lua" - This is the core script that defines the wand's unique behavior and spell generation.

### Mana Reloader Component

*   `_tags`: "enabled_in_world,enabled_in_hand,enabled_in_inventory" - This component ensures mana regeneration is active in various game states.