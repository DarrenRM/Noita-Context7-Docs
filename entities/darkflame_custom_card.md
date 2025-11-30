---
title: Darkflame Custom Card
category: entities
---

# Darkflame Custom Card

This document details the configuration for the "Darkflame" custom card entity in Noita, intended for AI-assisted modding.

## Base Entity Configuration

The card inherits from `base_custom_card.xml`, providing fundamental properties.

### Sprite Component

Defines the visual representation of the card in the UI.

*   **`image_file`**: `data/ui_gfx/gun_actions/darkflame.png` - Specifies the texture used for the card's icon.

### Item Action Component

Assigns an action ID to the card, enabling its functionality.

*   **`action_id`**: `DARKFLAME` - The unique identifier for this card's action.
*   **`_tags`**: `enabled_in_world` - Indicates the card is active when in the game world.

## Inherited Transform Component

Manages the positioning of the card when held.

*   **`_tags`**: `enabled_in_world`, `enabled_in_hand` - The transform is applied when the card is in the world and held by the player.
*   **`position.x`**: `8` - Offset on the X-axis.
*   **`position.y`**: `0` - Offset on the Y-axis.

## Sprite Particle Emitter Component

Responsible for generating visual particle effects associated with the card.

*   **`_tags`**: `enabled_in_hand`, `item_identified` - Particles are active when the item is held and identified.
*   **`sprite_file`**: `data/particles/darkflame.xml` - Links to the particle definition file.
*   **`delay`**: `0` - No initial delay before emission.
*   **`lifetime`**: `0` - Particles have no inherent lifetime (controlled by other factors).
*   **`color.r`, `color.g`, `color.b`, `color.a`**: `1`, `1`, `1`, `0.2` - Initial color (white with low alpha).
*   **`gravity.y`**: `10` - Applies a downward gravitational pull to particles.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `10`, `15` - Controls the timing between particle emissions.
*   **`count_min`, `count_max`**: `1`, `1` - Emits a single particle per emission cycle.
*   **Randomization**: Various `randomize_` attributes control the spread and initial velocity/rotation of emitted particles, creating a dynamic visual effect.

## Light Component

Adds a light source originating from the card.

*   **`_tags`**: `enabled_in_hand`, `item_identified` - The light is active when the item is held and identified.
*   **`_enabled`**: `1` - The light component is active.
*   **`radius`**: `64` - The range of the light.
*   **`fade_out_time`**: `1.5` - How long the light takes to fade.
*   **`r`, `g`, `b`**: `180`, `40`, `220` - Defines the light color (a purplish hue).