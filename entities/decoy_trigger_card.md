---
title: Decoy Trigger Card
category: entities
---

# Decoy Trigger Card

This entity defines the "Decoy Trigger" custom card in Noita. It's a special item that, when used, creates a decoy.

## Base Entity

The card inherits its core functionality from `base_custom_card.xml`.

### Key Components:

*   **`SpriteComponent`**:
    *   `image_file`: `data/ui_gfx/gun_actions/decoy_trigger.png` - Specifies the visual representation of the card in the UI.
*   **`ItemActionComponent`**:
    *   `_tags`: `enabled_in_world` - Indicates this action is available when the item is in the game world.
    *   `action_id`: `DECOY_TRIGGER` - The unique identifier for this item's action.

## Visual and Effect Components

These components define the visual flair and effects when the card is held or identified.

### Key Components:

*   **`InheritTransformComponent`**:
    *   `_tags`: `enabled_in_world,enabled_in_hand` - Applies when the item is in the world or being held.
    *   `Transform`:
        *   `position.x`: `8`
        *   `position.y`: `0` - Defines a slight offset for the item's transform.
*   **`SpriteParticleEmitterComponent`**:
    *   `_tags`: `enabled_in_hand,item_identified` - Activates when the item is held and identified.
    *   `sprite_file`: `data/particles/shine_03.xml` - Uses a shine particle effect.
    *   `lifetime`: `1.5` - The duration of the particle effect.
    *   `color.r`, `color.g`, `color.b`, `color.a`: `1, 1, 1, 1` - White, fully opaque color.
    *   `color_change.a`: `-1` - Alpha fades out over the lifetime.
    *   `gravity.y`: `20` - Particles are affected by gravity.
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: `25`, `40` - Controls the timing of particle emissions.
    *   `count_min`, `count_max`: `1`, `1` - Emits one particle at a time.
    *   `randomize_rotation`, `randomize_angular_velocity`, `randomize_position`, `randomize_velocity`: These attributes introduce variations in particle behavior, creating a dynamic shine effect.
*   **`LightComponent`**:
    *   `_tags`: `enabled_in_hand,item_identified` - Activates when the item is held and identified.
    *   `_enabled`: `1` - The light component is enabled.
    *   `radius`: `30` - The radius of the light.
    *   `fade_out_time`: `1.5` - How long the light takes to fade out.
    *   `r`, `g`, `b`: `80, 10, 80` - A purple-ish light color.