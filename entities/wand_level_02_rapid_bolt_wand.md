---
title: Wand Level 02 (Rapid Bolt Wand)
category: entities
---

# Wand Level 02 (Rapid Bolt Wand)

This entity defines a basic wand item in Noita, specifically the "Rapid bolt wand". It inherits properties from `base_item.xml` and `base_wand.xml`, and customizes its behavior through the `AbilityComponent` and a Lua script.

## Key Components and Attributes

### Base Item and Wand Properties

*   **`Base file="data/entities/base_item.xml"`**: Inherits fundamental item properties.
    *   **`SpriteComponent`**: Defines visual aspects, including animations. `next_rect_animation="JobAbilityMachinegun"` suggests a specific animation set.
    *   **`ItemComponent`**: Handles item-specific behaviors like hover animations. `play_hover_animation="1"` enables this.
    *   **`SimplePhysicsComponent _enabled="0"`**: Indicates physics are disabled for this item.
*   **`Base file="data/entities/base_wand.xml"`**: Inherits core wand mechanics.

### Ability Component (Wand Functionality)

This component dictates the wand's firing mechanics and properties.

*   **`amount_in_inventory="1"`**: The default quantity when found.
*   **`cooldown_frames="0"`**: No cooldown between firing actions.
*   **`drop_as_item_on_death="1"`**: The wand will drop as an item if the player dies.
*   **`entity_count="1"`**: Refers to the number of projectiles fired per shot.
*   **`mana_charge_speed="60"`**: How quickly mana regenerates.
*   **`mana_max="200"`**: The maximum mana capacity of the wand.
*   **`max_amount_in_inventory="1"`**: Only one of this wand can be held.
*   **`ui_name="Rapid bolt wand"`**: The name displayed in the game's UI.
*   **`use_gun_script="1"`**: Indicates that a custom script controls the firing behavior.

#### `gun_config`

*   **`actions_per_round="1"`**: One action (projectile) per firing cycle.
*   **`shuffle_deck_when_empty="1"`**: The spell deck will shuffle when depleted.
*   **`reload_time="18"`**: Time in frames to reload the spell deck.
*   **`deck_capacity="8"`**: The wand can hold up to 8 spells in its deck.

#### `gunaction_config`

*   **`fire_rate_wait="5"`**: The delay in frames between consecutive shots.

### Sprite and Hotspot

*   **`sprite_file="data/items_gfx/machinegun.xml"`**: Specifies the graphical asset for the wand's appearance.
*   **`HotspotComponent _tags="shoot_pos"`**: Defines the origin point for projectiles.
    *   **`offset.x="20"`**: The horizontal offset of the shooting position.
    *   **`offset.y="0"`**: The vertical offset of the shooting position.

### Lua Scripting

*   **`LuaComponent _enabled="1"`**: Enables the attached Lua script.
    *   **`execute_on_added="1"`**: The script runs immediately when the wand is added to the game.
    *   **`remove_after_executed="1"`**: The script is removed after its initial execution.
    *   **`script_source_file="data/scripts/gun/procedural/wand_level_02.lua"`**: The path to the custom Lua script that defines the wand's procedural generation and behavior.

### Mana Reloader

*   **`ManaReloaderComponent _tags="enabled_in_world,enabled_in_hand,enabled_in_inventory"`**: This component likely handles the automatic mana regeneration for the wand, active in various game states.