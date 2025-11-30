---
title: Wand Level 04 (Rapid Bolt Wand)
category: entities
---

---

# Wand Level 04 (Rapid Bolt Wand)

This document details the configuration for a Level 04 Wand in Noita, specifically the "Rapid bolt wand". It inherits base wand functionality and customizes its firing behavior and appearance.

## Core Components

### Base Wand Functionality

The wand inherits core mechanics from `base_wand_physics.xml` and `base_wand.xml`.

### Sprite Component

*   `next_rect_animation`: "JobAbilityMachinegun" - Defines the animation sequence for the wand's sprite.

### Item Component

*   `play_hover_animation`: "1" - Enables a hover animation when the item is being inspected or held.

## Ability Component (Wand Specifics)

This component defines the wand's unique properties and firing mechanics.

*   `ui_name`: "Rapid bolt wand" - The in-game name displayed to the player.
*   `sprite_file`: "data/items_gfx/machinegun.xml" - Specifies the graphical asset for the wand.
*   `mana_max`: "400" - The maximum mana capacity of the wand.
*   `mana_charge_speed`: "100" - How quickly the wand recharges mana.
*   `drop_as_item_on_death`: "1" - The wand will be dropped as an item when the player dies.
*   `amount_in_inventory`: "1" - Default quantity when picked up.
*   `max_amount_in_inventory`: "1" - Maximum quantity that can be held.
*   `use_gun_script`: "1" - Indicates that a custom script governs the gun's behavior.

### Gun Configuration (`gun_config`)

*   `reload_time`: "18" - Frames required to reload the wand after firing its deck.
*   `deck_capacity`: "8" - The number of spells that can be held in the wand's spell deck.
*   `shuffle_deck_when_empty`: "1" - The spell deck is shuffled when it becomes empty.
*   `actions_per_round`: "1" - Number of actions performed per firing cycle.

### Gun Action Configuration (`gunaction_config`)

*   `fire_rate_wait`: "5" - Frames to wait between individual spell casts within a single firing action.

## Hotspot Component

*   `_tags`: "shoot_pos" - Marks this as the position from which projectiles are fired.
*   `offset.x`: "20" - Horizontal offset of the firing position from the wand's center.
*   `offset.y`: "0" - Vertical offset of the firing position from the wand's center.

## Lua Component

*   `script_source_file`: "data/scripts/gun/procedural/wand_level_04.lua" - The custom Lua script that controls the wand's procedural generation and firing logic.
*   `execute_on_added`: "1" - The script runs immediately when the wand is added to the game.
*   `remove_after_executed`: "1" - The Lua component is removed after its initial execution.

## Mana Reloader Component

*   `_tags`: "enabled_in_world,enabled_in_hand,enabled_in_inventory" - This component is active in all states (world, hand, inventory). It likely handles mana regeneration.