---
title: Blindness Card Entity
category: entities
---

# Blindness Card Entity

This document describes the Noita entity responsible for the "Blindness" custom card. It details its visual representation, in-game action, and particle/light effects when held.

## Base Entity Configuration

The core of this entity is based on `base_custom_card.xml`, providing fundamental properties for custom cards.

### Sprite Component

Defines the visual appearance of the card in the game's UI.

*   **`image_file`**: `data/ui_gfx/gun_actions/blindness.png` - Specifies the texture used for the card's icon.

### Item Action Component

Determines the in-game functionality and identification of the card.

*   **`_tags`**: `enabled_in_world` - Indicates the card is active and usable within the game world.
*   **`action_id`**: `BLINDNESS` - A unique identifier for this specific card action.

## Transform Component

Controls the positioning of the card when held by the player.

### Inherit Transform Component

*   **`_tags`**: `enabled_in_world,enabled_in_hand` - The transform is applied when the card is in the world and being held.
*   **`Transform`**:
    *   **`position.x`**: `8` - Offset on the X-axis.
    *   **`position.y`**: `0` - Offset on the Y-axis.

## Particle Emitter Component

Manages the visual particle effects associated with the card when it's identified and held.

### Sprite Particle Emitter Component

*   **`_tags`**: `enabled_in_hand,item_identified` - Particles are emitted when the item is held and identified.
*   **`sprite_file`**: `data/particles/puff_04.xml` - The particle sprite used for the effect.
*   **`delay`**: `0` - No initial delay before emission starts.
*   **`lifetime`**: `2` - Duration of each particle in seconds.
*   **Color Properties**:
    *   `color.r`, `color.g`, `color.b`, `color.a`: `1, 1, 1, 1` - Initial white color.
    *   `color_change.a`: `-2` - Alpha value decreases over the particle's lifetime, causing fading.
*   **Emission Properties**:
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: `24`, `45` - Controls the timing between particle bursts.
    *   `count_min`, `count_max`: `1`, `2` - Number of particles emitted per burst.
*   **Randomization**: Various parameters (`rotation`, `angular_velocity`, `position`, `velocity`) are randomized within specified ranges to create a dynamic visual effect.

## Light Component

Adds a dynamic light source when the card is identified and held.

### Light Component

*   **`_tags`**: `enabled_in_hand,item_identified` - Light is active when the item is held and identified.
*   **`_enabled`**: `1` - The light component is enabled by default.
*   **`radius`**: `30` - The radius of the light's influence.
*   **`fade_out_time`**: `1.5` - How long the light takes to fade out.
*   **Color Properties**:
    *   `r`, `g`, `b`: `20`, `80`, `80` - Defines a bluish-green light color.