---
title: Teleport Projectile (Short) Card
category: data
---

# Teleport Projectile (Short) Card

This document describes the `teleport_projectile_short.xml` entity, which defines a custom wand card in Noita. This card, when equipped, allows the player to cast a short-range teleport projectile.

## Key Components

### Base Entity (`<Base>`)

This element inherits functionality from `data/entities/base_custom_card.xml`, providing the fundamental structure for a custom wand card.

*   **`<SpriteComponent>`**: Defines the visual representation of the card in the UI.
    *   `image_file`: `data/ui_gfx/gun_actions/teleport_projectile_short.png` - Specifies the sprite used for the card's icon.

*   **`<ItemActionComponent>`**: Links the card to a specific in-game action.
    *   `action_id`: `TELEPORT_PROJECTILE_SHORT` - The unique identifier for the action this card performs.
    *   `_tags`: `enabled_in_world` - Indicates this action is active when the item is in the game world.

### Transform (`<InheritTransformComponent>`)

This component manages the positioning of the card's visual elements when held.

*   **`<Transform>`**:
    *   `position.x`: `8` - Offset on the X-axis.
    *   `position.y`: `0` - Offset on the Y-axis.

### Particle Effects (`<SpriteParticleEmitterComponent>`)

This component adds visual flair to the card when it's identified or held.

*   **`_tags`**: `enabled_in_hand`, `item_identified` - Controls when these particles are active.
*   **`sprite_file`**: `data/particles/shine_02.xml` - The particle sprite used.
*   **`lifetime`**: `2` - Duration of the particle effect in seconds.
*   **`color`**: `r="1" g="1" b="1" a="1"` - Initial color (white).
*   **`color_change`**: `a="-1"` - Alpha (transparency) decreases over time.
*   **`gravity`**: `y="10"` - Particles are affected by gravity.
*   **`emission_interval_min_frames`**: `34`
*   **`emission_interval_max_frames`**: `55`
*   **`count_min`**: `1`
*   **`count_max`**: `2`
*   **`randomize_rotation`**: `min="-3.1415" max="3.1415"` - Randomizes particle rotation.
*   **`randomize_angular_velocity`**: `min="-1" max="1"` - Randomizes particle spinning.
*   **`randomize_position`**: Offsets the spawn position within a small radius.
*   **`randomize_velocity`**: Offsets the initial velocity of particles.

### Light Effect (`<LightComponent>`)

Adds a subtle glow to the card when identified or held.

*   **`_tags`**: `enabled_in_hand`, `item_identified` - Controls when the light is active.
*   **`radius`**: `30` - The range of the light.
*   **`fade_out_time`**: `1.5` - How long the light takes to fade.
*   **`r`, `g`, `b`**: `20`, `80`, `80` - The color of the light (a teal hue).