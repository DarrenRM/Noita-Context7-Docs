---
title: Wand Unshuffle 05
category: entities
---

# Wand Unshuffle 05

This entity defines a specific type of wand in Noita, characterized by its unique projectile behavior and visual representation. It inherits base functionality from `base_item.xml` and `base_wand.xml`.

## Key Components and Attributes

### Base Item and Wand Properties

*   **`Base file="data/entities/base_item.xml"`**: Inherits fundamental item properties.
    *   **`SpriteComponent`**: Defines the visual appearance and animations.
        *   `next_rect_animation="JobAbilityMachinegun"`: Specifies the animation sequence for the sprite.
    *   **`ItemComponent`**: Handles item-specific interactions.
        *   `play_hover_animation="1"`: Enables a hover animation when the item is interacted with.
    *   **`SimplePhysicsComponent`**: Manages physics, but is disabled (`_enabled="0"`) for this wand.

*   **`Base file="data/entities/base_wand.xml"`**: Inherits core wand mechanics.

### Ability Component (Wand Functionality)

This component dictates the wand's firing behavior, mana management, and inventory handling.

*   **`AbilityComponent`**:
    *   `ui_name="Rapid bolt wand"`: The display name of the wand in the game's UI.
    *   `sprite_file="data/items_gfx/machinegun.xml"`: Specifies the graphical asset used for the wand's sprite.
    *   `mana_max="400"`: The maximum mana capacity of the wand.
    *   `mana_charge_speed="100"`: The rate at which mana regenerates.
    *   `cooldown_frames="0"`: No cooldown between firing actions.
    *   `reload_time_frames="0"`: No reload time after emptying the deck.
    *   `drop_as_item_on_death="1"`: The wand will be dropped as an item if the player dies.
    *   `amount_in_inventory="1"`: The default quantity of this wand when picked up.
    *   `max_amount_in_inventory="1"`: Only one of this wand can be held at a time.
    *   `use_gun_script="1"`: Indicates that a custom script controls the gun's behavior.

#### Gun Configuration (`gun_config`)

*   `actions_per_round="1"`: The wand performs one action per firing cycle.
*   `shuffle_deck_when_empty="0"`: The spell deck does not shuffle when it becomes empty.
*   `reload_time="18"`: The time in frames it takes to reload the wand's spell deck.
*   `deck_capacity="8"`: The maximum number of spells that can be held in the wand's deck.

#### Gun Action Configuration (`gunaction_config`)

*   `fire_rate_wait="5"`: The delay in frames between consecutive shots.

### Hotspot Component

*   **`HotspotComponent`**: Defines points of interaction or origin for actions.
    *   `_tags="shoot_pos"`: Marks this hotspot as the origin for shooting projectiles.
    *   `offset.x="20"`: Horizontal offset for the shooting position.
    *   `offset.y="0"`: Vertical offset for the shooting position.

### Lua Component

*   **`LuaComponent`**: Executes custom Lua scripts.
    *   `script_source_file="data/scripts/gun/procedural/wand_unshuffle_05.lua"`: This is the core script that defines the unique "unshuffle" behavior of this wand, likely influencing how spells are drawn and cast from its deck.
    *   `execute_on_added="1"`: The script runs immediately when the entity is added.
    *   `remove_after_executed="1"`: The Lua component is removed after its initial execution.

### Mana Reloader Component

*   **`ManaReloaderComponent`**: Manages mana regeneration for the wand.
    *   `_tags="enabled_in_world,enabled_in_hand,enabled_in_inventory"`: The mana reloader is active in all relevant game states.