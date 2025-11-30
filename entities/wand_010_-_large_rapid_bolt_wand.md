---
title: Wand 010 - Large Rapid Bolt Wand
category: entities
---

# Wand 010 - Large Rapid Bolt Wand

This document describes the `wand_010.xml` entity, a wand found in the early levels of Noita. It's designed for rapid projectile firing with a moderate mana pool.

## Key Attributes

The `wand_010.xml` entity defines a wand with the following primary characteristics:

*   **`name`**: `wand_010` (Internal identifier)
*   **`tags`**: `teleportable_NOT,item,wand` (Indicates it's an item, a wand, and cannot be teleported)
*   **`ui_name`**: `Large Rapid bolt wand` (The name displayed to the player)
*   **`sprite_file`**: `data/items_gfx/wands/wand_0326.png` (Visual representation of the wand)

## Ability Component

This component governs the wand's magical capabilities.

### Core Properties

*   **`mana`**: `210` (The total mana the wand holds)
*   **`mana_max`**: `210` (The maximum mana the wand can hold)
*   **`mana_charge_speed`**: `46` (How quickly mana regenerates)
*   **`charge_wait_frames`**: `10` (Delay between shots)
*   **`item_recoil_max`**: `1` (Maximum recoil when firing)
*   **`item_recoil_recovery_speed`**: `15` (How quickly recoil resets)
*   **`rotate_in_hand`**: `1` (The wand rotates in the player's hand)
*   **`rotate_hand_amount`**: `0.7` (The speed of rotation in hand)

### Gun Configuration

Defines the wand's firing mechanics.

*   **`deck_capacity`**: `3` (The number of spells that can be held in the wand's "deck")
*   **`reload_time`**: `26` (Frames to reload the wand)
*   **`actions_per_round`**: `1` (Number of actions performed per shot)

### Gun Action Configuration

Details the properties of the projectiles fired by the wand.

*   **`action_mana_drain`**: `10` (Mana cost per shot)
*   **`speed_multiplier`**: `1.05598` (Increases projectile speed)
*   **`fire_rate_wait`**: `3` (Additional delay between firing actions within a round)
*   **`spread_degrees`**: `-1` (Negative spread can indicate a tighter shot pattern or specific behavior)

## Hotspot Component

Defines the firing point of the wand.

*   **`offset.x`**: `7` (Horizontal offset of the shooting position)
*   **`offset.y`**: `0` (Vertical offset of the shooting position)

## Sprite Component

Specifies the visual offset of the wand's sprite.

*   **`offset_x`**: `1` (Horizontal offset of the sprite)
*   **`offset_y`**: `3` (Vertical offset of the sprite)