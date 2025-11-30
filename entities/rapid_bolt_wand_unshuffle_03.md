---
title: Rapid Bolt Wand (Unshuffle 03)
category: entities
---

---

# Rapid Bolt Wand (Unshuffle 03)

This document details the configuration for the "Rapid bolt wand" entity in Noita, specifically focusing on its AI-assisted modding potential.

## Core Functionality

The `Rapid bolt wand` is a projectile-firing item with a focus on rapid fire and a specific spell-shuffling behavior.

### Key Attributes

*   **`ui_name`**: "Rapid bolt wand" - The in-game name displayed to the player.
*   **`sprite_file`**: `data/items_gfx/machinegun.xml` - Defines the visual appearance of the wand.
*   **`mana_max`**: `300` - The maximum mana capacity of the wand.
*   **`mana_charge_speed`**: `80` - How quickly the wand recharges mana.
*   **`drop_as_item_on_death`**: `1` - The wand will be dropped as an item when the player dies.
*   **`use_gun_script`**: `1` - Indicates that the wand utilizes a custom script for its firing behavior.

## Gun Configuration

The `gun_config` element governs the fundamental mechanics of how the wand fires spells.

### Key Attributes

*   **`actions_per_round`**: `1` - The number of spell actions performed per firing cycle.
*   **`shuffle_deck_when_empty`**: `0` - When the spell deck is empty, it will *not* automatically shuffle. This implies a manual shuffle or a specific spell interaction is required.
*   **`reload_time`**: `18` - The base reload time in frames between firing cycles.
*   **`deck_capacity`**: `8` - The maximum number of spells that can be held in the wand's spell deck.

## Gun Action Configuration

The `gunaction_config` refines the timing and behavior of spell actions.

### Key Attributes

*   **`fire_rate_wait`**: `5` - The wait time in frames between individual spell actions within a single firing cycle. This contributes to the rapid-fire nature.

## Scripting

The `LuaComponent` is crucial for defining the wand's unique behavior, particularly its spell selection and firing logic.

### Key Attributes

*   **`script_source_file`**: `data/scripts/gun/procedural/wand_unshuffle_03.lua` - This points to the external Lua script that controls the wand's advanced functionalities, including its "unshuffle" behavior.
*   **`execute_on_added`**: `1` - The script will execute automatically when the wand is added to the game.
*   **`remove_after_executed`**: `1` - The script will be removed after its initial execution, suggesting it sets up the wand's state rather than running continuously.

## Visuals and Physics

The wand inherits base properties from other entities for its visual representation and physical interactions.

### Key Components

*   **`Base file="data/entities/base_wand_physics.xml"`**: Inherits physics properties and basic wand behavior.
    *   **`SpriteComponent`**:
        *   **`next_rect_animation`**: "JobAbilityMachinegun" - Specifies an animation for the sprite.
    *   **`ItemComponent`**:
        *   **`play_hover_animation`**: `1` - Enables a hover animation when the item is in hand.
*   **`Base file="data/entities/base_wand.xml"`**: Inherits general wand functionalities.
*   **`HotspotComponent`**:
    *   **`offset.x`**: `20` - Defines the horizontal offset for the shooting position.
    *   **`offset.y`**: `0` - Defines the vertical offset for the shooting position.
*   **`ManaReloaderComponent`**: Enables mana regeneration for the wand in various states (world, hand, inventory).

## AI Modding Considerations

For AI-assisted modding, the most impactful elements are:

1.  **`AbilityComponent`**: Modifying `mana_max`, `mana_charge_speed`, and `reload_time` directly impacts the wand's combat effectiveness and resource management.
2.  **`gun_config`**: Adjusting `deck_capacity` and `reload_time` can significantly alter the spellcasting rhythm. The `shuffle_deck_when_empty="0"` attribute is particularly interesting for custom spell logic.
3.  **`LuaComponent`**: The `script_source_file` is the primary entry point for advanced AI modding. Understanding and modifying `wand_unshuffle_03.lua` will allow for custom spell selection, firing patterns, and unique "unshuffle" mechanics.
4.  **`HotspotComponent`**: Fine-tuning `offset.x` and `offset.y` can alter projectile trajectory and aiming.