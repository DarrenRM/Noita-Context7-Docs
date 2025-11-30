---
title: Good Rapid Bolt Wand
category: entities
---

# Good Rapid Bolt Wand

This document details the configuration for the "Good Rapid Bolt Wand" entity in Noita, intended for AI-assisted modding.

## Core Entity Properties

*   **`name`**: `wand_001` (Internal identifier)
*   **`serialize`**: `1` (Indicates the entity should be saved and loaded)
*   **`tags`**: `hittable` (Can be targeted and damaged)

## Key Components

### `AbilityComponent`

This component defines the wand's core functionality and stats.

*   **`ui_name`**: "Good Rapid bolt wand" (The name displayed in-game)
*   **`sprite_file`**: `data/items_gfx/wands/wand_0484.png` (Visual representation of the wand)
*   **`mana`**: `220` (Maximum mana capacity)
*   **`mana_max`**: `220` (Maximum mana capacity)
*   **`mana_charge_speed`**: `45` (Speed at which mana regenerates)
*   **`charge_wait_frames`**: `10` (Delay between shots)
*   **`reload_time_frames`**: `27` (Time to reload the wand)
*   **`item_recoil_max`**: `1` (Maximum recoil applied to the player)
*   **`item_recoil_offset_coeff`**: `1` (Coefficient for recoil offset)
*   **`item_recoil_rotation_coeff`**: `5` (Coefficient for recoil rotation)
*   **`rotate_in_hand`**: `1` (Wand rotates in the player's hand)
*   **`rotate_in_hand_amount`**: `1` (Amount of rotation in hand)

#### `gun_config`

Defines the wand's deck and firing behavior.

*   **`deck_capacity`**: `7` (Number of spells the wand can hold)
*   **`reload_time`**: `27` (Reload time in frames)
*   **`shuffle_deck_when_empty`**: `1` (Shuffles the spell deck when it's empty)
*   **`actions_per_round`**: `1` (Number of actions performed per shot)

#### `gunaction_config`

Defines the properties of the projectile fired by the wand.

*   **`speed_multiplier`**: `1.03398` (Increases projectile speed)
*   **`spread_degrees`**: `8` (Spread angle of the projectiles)
*   **`fire_rate_wait`**: `2` (Delay between firing actions within a round)
*   **`action_mana_drain`**: `10` (Mana cost per action)

### `ItemComponent`

Standard item properties.

*   **`is_identified`**: `1` (The wand is identified from the start)
*   **`is_pickable`**: `1` (Can be picked up by the player)
*   **`preferred_inventory`**: `QUICK` (Defaults to the quick inventory slot)
*   **`play_hover_animation`**: `1` (Plays a hover animation when in inventory)

### `SpriteComponent`

Defines the visual appearance of the wand when held or in the world.

*   **`image_file`**: `data/items_gfx/wands/wand_0484.png` (Matches the `sprite_file` in `AbilityComponent`)
*   **`offset_x`**: `2`
*   **`offset_y`**: `2`
*   **`z_index`**: `0.595` (Determines rendering order)

### `SpriteParticleEmitterComponent`

Responsible for visual effects, likely a muzzle flash or projectile trail.

*   **`sprite_file`**: `data/particles/ray.xml` (Uses a "ray" particle effect)
*   **`lifetime`**: `1.5` (Duration of the particle effect in seconds)
*   **`color.r`**: `1`, **`color.g`**: `1`, **`color.b`**: `1`, **`color.a`**: `0.5` (White with 50% opacity)
*   **`randomize_position.max_x`**: `5`, **`randomize_position.max_y`**: `5` (Particles spawn within a small radius)
*   **`randomize_velocity.max_x`**: `30`, **`randomize_velocity.max_y`**: `30` (Particles have a random outward velocity)
*   **`scale_velocity.x`**: `-0.2`, **`scale_velocity.y`**: `4` (Particles shrink and grow)

### `LuaComponent`

Links to a Lua script that further defines or modifies the wand's behavior.

*   **`script_source_file`**: `data/scripts/gun/procedural/level_1_wand.lua` (The script controlling procedural generation or specific behaviors for this wand tier)

### `Base`

Inherits properties from a base wand pickup entity.

*   **`file`**: `data/entities/base_wand_pickup.xml`

## Summary

The "Good Rapid Bolt Wand" is a mid-tier wand characterized by its relatively fast firing rate (`charge_wait_frames: 10`), moderate mana capacity (`mana: 220`), and a decent deck size (`deck_capacity: 7`). The `speed_multiplier` and `spread_degrees` on its projectiles suggest it's designed for consistent damage output at medium range. The associated Lua script likely handles its procedural generation or specific spell combinations.