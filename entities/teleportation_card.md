---
title: Teleportation Card
category: entities
---

# Teleportation Card

This document details the configuration for the "Teleportation" custom card entity in Noita, intended for AI-assisted modding.

## Entity Definition

The core of this entity is based on `base_custom_card.xml`, providing fundamental properties for a custom card.

### Key Components

*   **`Base`**: Inherits from `base_custom_card.xml`.
    *   **`SpriteComponent`**: Defines the visual representation of the card in the UI.
        *   `image_file`: `data/ui_gfx/gun_actions/teleportation.png` - Specifies the texture for the card's icon.
    *   **`ItemActionComponent`**: Assigns an action ID to the card.
        *   `action_id`: `TELEPORTATION` - Identifies the specific action this card performs.
        *   `_tags`: `enabled_in_world` - Indicates the card is active when in the game world.

*   **`InheritTransformComponent`**: Manages the card's position relative to its parent (e.g., the player's hand).
    *   `_tags`: `enabled_in_world,enabled_in_hand` - The transform is active when the card is in the world or held.
    *   **`Transform`**: Defines the offset.
        *   `position.x`: `8`
        *   `position.y`: `0`

*   **`SpriteParticleEmitterComponent`**: Controls particle effects associated with the card when held and identified.
    *   `_tags`: `enabled_in_hand,item_identified` - Effects are active when the item is held and its identity is revealed.
    *   `sprite_file`: `data/particles/shine_02.xml` - Uses a predefined shine particle effect.
    *   `lifetime`: `2` - Duration of the particle effect.
    *   `color.r`, `color.g`, `color.b`, `color.a`: `1, 1, 1, 1` - Initial white color.
    *   `color_change.a`: `-1` - Alpha value decreases over time.
    *   `gravity.y`: `10` - Particles are affected by gravity.
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: `24`, `45` - Controls the timing between particle emissions.
    *   `count_min`, `count_max`: `1`, `2` - Number of particles emitted per interval.
    *   `randomize_rotation`, `randomize_angular_velocity`, `randomize_position`, `randomize_velocity`: Various parameters to introduce variation in particle behavior, creating a dynamic visual effect.

*   **`LightComponent`**: Adds a light source when the card is held and identified.
    *   `_tags`: `enabled_in_hand,item_identified` - Light is active under the same conditions as particle effects.
    *   `_enabled`: `1` - The light component is active.
    *   `radius`: `30` - The range of the light.
    *   `fade_out_time`: `1.5` - How long the light takes to fade.
    *   `r`, `g`, `b`: `20`, `80`, `80` - Defines a teal-like color for the light.