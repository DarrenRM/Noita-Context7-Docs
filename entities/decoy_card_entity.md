---
title: Decoy Card Entity
category: entities
---

# Decoy Card Entity

This document describes the `decoy.xml` entity, which defines the Decoy wand card in Noita. It's a custom card entity designed to be used as a projectile or item.

## Key Components

### Base Entity (`base_custom_card.xml`)

This entity inherits from a base custom card, providing fundamental properties for wand cards.

*   **`SpriteComponent`**: Defines the visual representation of the Decoy card in the UI.
    *   `image_file`: `data/ui_gfx/gun_actions/decoy.png` - Specifies the texture used for the card's icon.

*   **`ItemActionComponent`**: Assigns an action ID to the card, enabling its functionality.
    *   `action_id`: `DECOY` - The unique identifier for the Decoy action.
    *   `_tags`: `enabled_in_world` - Indicates the card is active when in the game world.

### Transform Component (`InheritTransformComponent`)

This component manages the positioning and transformation of the Decoy card when held.

*   **`Transform`**: Defines the relative position of the card's sprite.
    *   `position.x`: `8`
    *   `position.y`: `0`

### Particle Emitter (`SpriteParticleEmitterComponent`)

This component creates visual particle effects associated with the Decoy card, particularly when identified.

*   **`_tags`**: `enabled_in_hand`, `item_identified` - Activates the emitter when the item is held and identified.
*   **`sprite_file`**: `data/particles/shine_03.xml` - The particle sprite to be used.
*   **`lifetime`**: `1.5` - Duration of the particle effect in seconds.
*   **`color.r`, `color.g`, `color.b`, `color.a`**: `1, 1, 1, 1` - Initial color of the particles (white).
*   **`color_change.a`**: `-1` - Alpha value decreases over time, causing particles to fade out.
*   **`gravity.y`**: `20` - Particles are affected by gravity.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `25`, `40` - Controls the timing between particle emissions.
*   **`count_min`, `count_max`**: `1`, `1` - Emits a single particle per emission cycle.
*   **Randomization**: Various `randomize_` attributes control the spread and initial velocity of particles, creating a dynamic visual effect.

### Light Component (`LightComponent`)

This component adds a light source to the Decoy card when it's held and identified.

*   **`_tags`**: `enabled_in_hand`, `item_identified` - Activates the light when the item is held and identified.
*   **`radius`**: `30` - The range of the light.
*   **`fade_out_time`**: `1.5` - How long the light takes to fade out.
*   **`r`, `g`, `b`**: `80, 10, 80` - The color of the light (a purplish hue).