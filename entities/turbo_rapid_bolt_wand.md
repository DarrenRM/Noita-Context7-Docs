---
title: Turbo Rapid Bolt Wand
category: entities
---

# Turbo Rapid Bolt Wand

This document details the configuration for the "Turbo Rapid Bolt Wand" entity in Noita, designed for AI-assisted modding.

## Core Entity Properties

*   **`name`**: `wand_009` (Internal identifier)
*   **`serialize`**: `1` (Indicates the entity should be saved and loaded)
*   **`tags`**: `hittable` (The wand can be hit by projectiles or other game elements)

## Transform Component

This component defines the initial position, rotation, and scale of the wand in the game world.

*   **`position.x`**: `928.586`
*   **`position.y`**: `-324.025`
*   **`rotation`**: `-2.93331`
*   **`scale.x`**: `1`
*   **`scale.y`**: `-1` (Flipped vertically)

## Ability Component (Wand Functionality)

This is the primary component defining the wand's behavior.

*   **`ui_name`**: "Turbo Rapid bolt wand" (The name displayed to the player)
*   **`sprite_file`**: `data/items_gfx/wands/wand_0724.png` (Visual representation of the wand)
*   **`mana`**: `160` (Initial mana capacity)
*   **`mana_max`**: `160` (Maximum mana capacity)
*   **`mana_charge_speed`**: `46` (Speed at which mana regenerates)
*   **`charge_wait_frames`**: `10` (Frames to wait before firing after charging)
*   **`reload_time_frames`**: `49` (Frames to reload the wand)
*   **`item_recoil_max`**: `1` (Maximum recoil applied to the player)
*   **`item_recoil_offset_coeff`**: `1` (Coefficient for recoil offset)
*   **`item_recoil_recovery_speed`**: `15` (Speed at which recoil recovers)
*   **`item_recoil_rotation_coeff`**: `5` (Coefficient for recoil rotation)
*   **`rotate_in_hand_amount`**: `1` (How much the wand rotates in the player's hand)
*   **`use_gun_script`**: `1` (Indicates that the wand uses a gun script for its firing logic)

### `gun_config`

*   **`deck_capacity`**: `6` (Number of spells the wand can hold)
*   **`reload_time`**: `49` (Frames to reload)
*   **`shuffle_deck_when_empty`**: `1` (The spell deck shuffles when it runs out of spells)

### `gunaction_config` (Default Action Configuration)

This section defines the properties of the wand's primary firing action.

*   **`action_mana_drain`**: `10` (Mana cost per shot)
*   **`speed_multiplier`**: `0.853983` (Reduces projectile speed)
*   **`spread_degrees`**: `3` (Angular spread of projectiles)
*   **`fire_rate_wait`**: `3` (Frames between shots when firing rapidly)

## Audio Loop Component

*   **`file`**: `data/audio/Desktop/items.bank`
*   **`event_name`**: `items/digger` (Likely plays a generic item pickup or equip sound)

## Item Component

Defines general item properties.

*   **`is_pickable`**: `1` (The wand can be picked up by the player)
*   **`is_identified`**: `1` (The wand's properties are known from the start)
*   **`preferred_inventory`**: `QUICK` (Suggests it should be placed in the quick inventory)
*   **`play_hover_animation`**: `1` (The wand will play a hover animation when in the inventory)

## Sprite Component

Controls the visual rendering of the wand.

*   **`image_file`**: `data/items_gfx/wands/wand_0724.png` (Same as `AbilityComponent` for consistency)
*   **`offset_x`**: `1`
*   **`offset_y`**: `1`
*   **`z_index`**: `0.595` (Determines rendering order)

## Sprite Particle Emitter Component

Responsible for visual effects, likely a subtle glow or aura.

*   **`sprite_file`**: `data/particles/ray.xml` (Uses a ray particle effect)
*   **`color.a`**: `0.5` (Semi-transparent)
*   **`color.b`**: `1`
*   **`color.g`**: `1`
*   **`color.r`**: `1` (White color)
*   **`lifetime`**: `1.5` (Duration of particles)
*   **`emission_interval_min_frames`**: `3`
*   **`emission_interval_max_frames`**: `6`
*   **`randomize_position.max_x`**: `5`
*   **`randomize_position.max_y`**: `5`
*   **`randomize_position.min_x`**: `-5`
*   **`randomize_position.min_y`**: `-5`
*   **`randomize_velocity.max_x`**: `30`
*   **`randomize_velocity.max_y`**: `30`
*   **`randomize_velocity.min_x`**: `-30`
*   **`randomize_velocity.min_y`**: `-30`
*   **`scale_velocity.x`**: `-0.2` (Particles shrink over time)
*   **`scale_velocity.y`**: `4` (Particles grow rapidly in height)
*   **`velocity_always_away_from_center`**: `1` (Particles move away from the wand's center)

## Lua Component

*   **`script_source_file`**: `data/scripts/gun/procedural/level_1_wand.lua` (This script likely handles the procedural generation of spells for this wand, contributing to its "rapid bolt" nature.)

## Base Component

*   **`file`**: `data/entities/base_wand_pickup.xml` (Inherits common properties for wand pickups)