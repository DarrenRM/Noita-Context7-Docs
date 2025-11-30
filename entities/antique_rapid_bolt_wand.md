---
title: Antique Rapid Bolt Wand
category: entities
---

# Antique Rapid Bolt Wand

This document details the configuration for the "Antique Rapid Bolt Wand" entity in Noita, designed for AI-assisted modding.

## Core Entity Properties

*   **`name`**: `wand_004` (Internal identifier)
*   **`serialize`**: `1` (Indicates the entity should be saved and loaded)
*   **`tags`**: `hittable` (Can be targeted by attacks)

## AbilityComponent (Wand Functionality)

This component defines the wand's core attributes and behavior.

*   **`ui_name`**: "Antique Rapid bolt wand" (Name displayed in-game)
*   **`sprite_file`**: `data/items_gfx/wands/wand_0516.png` (Visual representation of the wand)
*   **`mana`**: `190` (Total mana capacity)
*   **`mana_max`**: `190` (Maximum mana)
*   **`mana_charge_speed`**: `51` (Speed at which mana regenerates)
*   **`charge_wait_frames`**: `10` (Frames to wait before firing after mana is full)
*   **`reload_time_frames`**: `16` (Frames to reload the wand)
*   **`item_recoil_max`**: `1` (Maximum recoil when firing)
*   **`item_recoil_offset_coeff`**: `1` (Coefficient for recoil offset)
*   **`item_recoil_rotation_coeff`**: `5` (Coefficient for recoil rotation)
*   **`rotate_in_hand`**: `1` (Wand rotates in the player's hand)
*   **`rotate_hand_amount`**: `0.7` (Amount the player's hand rotates with the wand)
*   **`use_gun_script`**: `1` (Indicates a custom gun script is used)

### `gun_config`

Defines the wand's firing mechanics.

*   **`deck_capacity`**: `3` (Number of spells that can be held in the wand's deck)
*   **`actions_per_round`**: `1` (Number of actions performed per shot)
*   **`reload_time`**: `16` (Reload time in frames)

### `gunaction_config`

Defines the properties of the projectile fired by the wand.

*   **`speed_multiplier`**: `0.934037` (Multiplier for projectile speed)
*   **`fire_rate_wait`**: `23` (Frames to wait between firing actions)
*   **`action_mana_drain`**: `10` (Mana cost per action)
*   **`spread_degrees`**: `-1` (Spread angle of the projectile. Negative values might indicate a specific behavior or a default.)

## SpriteComponent (Visuals)

*   **`image_file`**: `data/items_gfx/wands/wand_0516.png` (The sprite file for the wand)
*   **`offset_x`**: `1`
*   **`offset_y`**: `5`
*   **`z_index`**: `0.595` (Determines rendering order)

## SpriteParticleEmitterComponent (Visual Effects)

This component adds particle effects to the wand.

*   **`sprite_file`**: `data/particles/ray.xml` (The particle sprite to use)
*   **`lifetime`**: `1.5` (Duration of each particle in seconds)
*   **`emission_interval_min_frames`**: `3`
*   **`emission_interval_max_frames`**: `6`
*   **`randomize_position.max_x`**: `5`
*   **`randomize_position.max_y`**: `5`
*   **`randomize_velocity.max_x`**: `30`
*   **`randomize_velocity.max_y`**: `30`
*   **`scale_velocity.x`**: `-0.2`
*   **`scale_velocity.y`**: `4`
*   **`color.a`**: `0.5`
*   **`color.b`**: `1`
*   **`color.g`**: `1`
*   **`color.r`**: `1`

## LuaComponent (Scripting)

*   **`script_source_file`**: `data/scripts/gun/procedural/level_1_wand.lua` (The Lua script that governs the wand's procedural generation and behavior)
*   **`execute_on_added`**: `1` (The script runs when the entity is added)
*   **`remove_after_executed`**: `1` (The script is removed after execution)

## Base File

*   **`Base file="data/entities/base_wand_pickup.xml"`**: Inherits properties from the base wand pickup entity.