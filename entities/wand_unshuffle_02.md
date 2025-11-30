---
title: Wand Unshuffle 02
category: entities
---

---

# Wand Unshuffle 02

This document describes the `wand_unshuffle_02.xml` entity, which defines a specific type of wand in Noita. This wand is characterized by its rapid firing rate and a unique deck shuffling behavior.

## Base Components

The wand inherits functionality from two base entity files:

*   `data/entities/base_item.xml`: Provides fundamental item properties like sprite handling and hover animations.
*   `data/entities/base_wand.xml`: Implements core wand mechanics.

## AbilityComponent

This component defines the wand's magical capabilities and behavior.

### Key Attributes:

*   `ui_name`: "Rapid bolt wand" - The name displayed in the game's UI.
*   `sprite_file`: `data/items_gfx/machinegun.xml` - Specifies the visual representation of the wand.
*   `mana_max`: `300` - The maximum mana capacity of the wand.
*   `mana_charge_speed`: `80` - How quickly the wand recharges mana.
*   `max_amount_in_inventory`: `1` - Only one of this wand can be held at a time.
*   `use_gun_script`: `1` - Indicates that a custom script is used for its firing behavior.

### Gun Configuration (`gun_config`):

*   `deck_capacity`: `8` - The number of spells that can be held in the wand's spell deck.
*   `reload_time`: `18` - The time in frames it takes to reload the wand after firing all spells in its deck.
*   `shuffle_deck_when_empty`: `0` - **Crucially, this is set to 0, meaning the deck does NOT shuffle when empty.** This implies a specific, non-randomized spell order or a different mechanism for spell selection.

### Gun Action Configuration (`gunaction_config`):

*   `fire_rate_wait`: `5` - The delay in frames between consecutive shots when firing rapidly.

## HotspotComponent

*   `_tags`: `shoot_pos` - Marks this component as the origin point for projectiles.
*   `offset.x`: `20` - The horizontal offset of the shooting position from the wand's center.
*   `offset.y`: `0` - The vertical offset of the shooting position from the wand's center.

## LuaComponent

This component links the wand to a custom script that dictates its unique behavior.

*   `script_source_file`: `data/scripts/gun/procedural/wand_unshuffle_02.lua` - The path to the Lua script responsible for the wand's firing logic and spell management.
*   `execute_on_added`: `1` - The script executes immediately when the wand is added to the game.
*   `remove_after_executed`: `1` - The Lua component is removed after its initial execution.

## ManaReloaderComponent

This component enables the wand to automatically reload its mana when in the world, in hand, or in inventory.