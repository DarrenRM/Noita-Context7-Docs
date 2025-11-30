---
title: Superior Rapid Bolt Wand
category: entities
---

# Superior Rapid Bolt Wand

This document details the configuration of the "Superior Rapid Bolt Wand" entity in Noita, intended for AI-assisted modding.

## Core Entity Properties

*   **`name`**: `wand_006` (Internal identifier)
*   **`serialize`**: `1` (Indicates the entity should be saved and loaded)
*   **`tags`**: `hittable` (Can be targeted and damaged)

## AbilityComponent

This component defines the wand's primary functionality and behavior.

*   **`ui_name`**: "Superior Rapid bolt wand" (The name displayed in-game)
*   **`sprite_file`**: `data/items_gfx/wands/wand_0058.png` (Visual representation of the wand)
*   **`mana`**: `250` (Maximum mana capacity)
*   **`mana_max`**: `250` (Maximum mana capacity)
*   **`mana_charge_speed`**: `49` (Speed at which mana regenerates)
*   **`charge_wait_frames`**: `10` (Frames to wait before firing after mana is full)
*   **`reload_time_frames`**: `23` (Frames to reload the wand)
*   **`item_recoil_max`**: `1` (Maximum recoil applied to the player)
*   **`item_recoil_offset_coeff`**: `1` (Coefficient for recoil offset)
*   **`item_recoil_rotation_coeff`**: `5` (Coefficient for recoil rotation)
*   **`rotate_in_hand`**: `1` (Wand rotates in the player's hand)
*   **`rotate_in_hand_amount`**: `1` (Magnitude of hand rotation)
*   **`use_gun_script`**: `1` (Indicates a custom gun script is used)

### `gun_config`

Defines the deck and firing mechanics of the wand.

*   **`deck_capacity`**: `6` (Number of spell slots in the wand's deck)
*   **`reload_time`**: `23` (Reload time in frames)
*   **`shuffle_deck_when_empty`**: `0` (Deck does not shuffle when empty)

### `gunaction_config`

Defines the properties of the projectile fired by the wand.

*   **`speed_multiplier`**: `0.985946` (Multiplier for projectile speed)
*   **`spread_degrees`**: `3` (Angular spread of projectiles)
*   **`fire_rate_wait`**: `13` (Frames to wait between firing actions)
*   **`action_mana_drain`**: `10` (Mana cost per action)

## SpriteComponent

Handles the visual rendering of the wand when it's in the world or in hand.

*   **`image_file`**: `data/items_gfx/wands/wand_0058.png` (The sprite file for the wand)
*   **`offset_x`**: `2` (X-axis offset for the sprite)
*   **`offset_y`**: `3` (Y-axis offset for the sprite)
*   **`z_index`**: `0.595` (Determines rendering order)

## SpriteParticleEmitterComponent

Responsible for visual effects, likely related to the wand's firing or idle state.

*   **`sprite_file`**: `data/particles/ray.xml` (Particle sprite file)
*   **`lifetime`**: `1.5` (Duration of particles in seconds)
*   **`emission_interval_min_frames`**: `3` (Minimum frames between particle emissions)
*   **`emission_interval_max_frames`**: `6` (Maximum frames between particle emissions)
*   **`randomize_position.max_x`**: `5` (Maximum random X offset for particles)
*   **`randomize_position.max_y`**: `5` (Maximum random Y offset for particles)
*   **`randomize_velocity.max_x`**: `30` (Maximum random X velocity for particles)
*   **`randomize_velocity.max_y`**: `30` (Maximum random Y velocity for particles)
*   **`scale_velocity.y`**: `4` (Velocity at which particle scale changes on the Y-axis)

## LuaComponent

Executes a Lua script to further define or modify the wand's behavior.

*   **`script_source_file`**: `data/scripts/gun/procedural/level_1_wand.lua` (The Lua script controlling procedural generation for level 1 wands)

## Base File

*   **`Base file`**: `data/entities/base_wand_pickup.xml` (Inherits properties from a base wand pickup entity)