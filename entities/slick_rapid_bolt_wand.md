---
title: Slick Rapid Bolt Wand
category: entities
---

# Slick Rapid Bolt Wand

This document describes the Noita wand entity `wand_014.xml`, which is a level 1 wand with a focus on rapid projectile firing.

## Key Attributes

The `wand_014.xml` entity primarily defines a wand with the following key characteristics:

*   **UI Name:** "Slick Rapid bolt wand"
*   **Sprite:** `data/items_gfx/wands/wand_0230.png`
*   **Base Wand:** Inherits properties from `data/entities/items/wands/level_01/base_wand_level_1.xml`.
*   **Mana:** 210 (max and initial)
*   **Mana Charge Speed:** 50
*   **Charge Wait Frames:** 10 (time between shots)
*   **Deck Capacity:** 2 (can hold 2 spells)
*   **Speed Multiplier (for projectiles):** 0.988051
*   **Spread Degrees:** 1 (slight spread on projectiles)

## Components

### AbilityComponent

This component governs the wand's functionality as a weapon.

*   **`charge_wait_frames`**: 10 - Determines the delay between consecutive shots.
*   **`mana`**: 210 - The amount of mana the wand starts with.
*   **`mana_max`**: 210 - The maximum mana capacity of the wand.
*   **`mana_charge_speed`**: 50 - How quickly the wand regenerates mana.
*   **`rotate_hand_amount`**: 0.7 - Controls the rotation of the wand in the player's hand.
*   **`sprite_file`**: `data/items_gfx/wands/wand_0230.png` - The visual representation of the wand.
*   **`ui_name`**: "Slick Rapid bolt wand" - The name displayed in the game's UI.

#### `gun_config`

This nested element configures the wand's shooting mechanics.

*   **`actions_per_round`**: 1 - The number of spells cast per shot.
*   **`deck_capacity`**: 2 - The maximum number of spells that can be loaded into the wand's deck.
*   **`reload_time`**: 12 - The time in frames it takes to reload the wand.
*   **`shuffle_deck_when_empty`**: 0 - The deck does not shuffle when empty.

#### `gunaction_config`

This element defines the properties of the spells cast by the wand.

*   **`action_mana_drain`**: 10 - The mana cost per spell cast.
*   **`fire_rate_wait`**: 6 - Additional delay between firing actions within a single round.
*   **`speed_multiplier`**: 0.988051 - Affects the projectile speed.
*   **`spread_degrees`**: 1 - The angular spread of the projectiles.

### HotspotComponent

Defines the origin point for shooting projectiles.

*   **`offset.x`**: 7
*   **`offset.y`**: 0

### SpriteComponent

Defines the visual sprite for the wand.

*   **`image_file`**: `data/items_gfx/wands/wand_0230.png`
*   **`offset_x`**: 1
*   **`offset_y`**: 3