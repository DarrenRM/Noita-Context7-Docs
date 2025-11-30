---
title: Experimental Wand 3
category: entities
---

# Experimental Wand 3

This document details the configuration for `experimental_wand_3`, an entity representing a wand in Noita, intended for AI-assisted modding.

## Core Entity Properties

The wand is defined as an `Entity` with the tag "wand".

## AbilityComponent

This component governs the wand's magical capabilities and behavior.

### Key Attributes:

*   `ui_name`: "experimental_wand_3" - The display name of the wand.
*   `mana_max`: 100 - The maximum mana capacity of the wand.
*   `mana_charge_speed`: 30 - The speed at which mana recharges.
*   `cooldown_frames`: 0 - No cooldown between shots.
*   `reload_time_frames`: 0 - Instant reload.
*   `amount_in_inventory`: 1 - The wand is found as a single item.
*   `max_amount_in_inventory`: 1 - Only one of this wand can be held.
*   `drop_as_item_on_death`: 1 - The wand will drop when the player dies.
*   `use_gun_script`: 1 - Indicates that the wand uses a gun script for its functionality.
*   `sprite_file`: "data/items_gfx/wands/custom/actual_wand.xml" - The visual representation of the wand.

### `gun_config`:

*   `deck_capacity`: 2 - The wand can hold up to 2 spells in its "deck".
*   `shuffle_deck_when_empty`: 0 - The spell deck does not shuffle when empty.
*   `reload_time`: 1 - A short reload time for the spell deck.

### `gunaction_config`:

*   `fire_rate_wait`: 1 - Minimal delay between firing actions.

## HotspotComponent

Defines the firing position for projectiles.

### Key Attributes:

*   `offset.x`: 15 - Horizontal offset of the firing point.
*   `offset.y`: 1 - Vertical offset of the firing point.

## Base Component

This section defines the item's base properties and visual elements.

### `ItemComponent`:

*   `item_name`: "experimental_wand_3" - Internal name for the item.
*   `play_hover_animation`: 1 - Enables a hover animation when the item is interacted with.

### `SpriteComponent`:

*   `image_file`: "data/items_gfx/wands/custom/actual_wand.xml" - The sprite used for the item in the world and hand.
*   `z_index`: -1.5 - Controls the layering of the sprite.

## LuaComponent

This component links the wand to its specific scripting logic.

### Key Attributes:

*   `script_source_file`: "data/entities/items/wands/experimental/experimental_wand_3.lua" - The path to the Lua script that defines the wand's unique behavior.
*   `execute_on_added`: 1 - The script runs when the wand is added to the game.
*   `remove_after_executed`: 1 - The script is removed after its initial execution.

## ManaReloaderComponent

This component enables the wand to passively regenerate mana.