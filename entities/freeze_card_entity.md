---
title: Freeze Card Entity
category: entities
---

# Freeze Card Entity

This document describes the `freeze.xml` entity, which defines the "Freeze" spell card in Noita. It details its visual representation, item action, and particle effects when held by the player.

## Key Components

### Base Entity (`Base`)

This component inherits from `base_custom_card.xml`, providing the fundamental structure for a custom spell card.

*   **`SpriteComponent`**:
    *   `image_file`: `data/ui_gfx/gun_actions/freeze.png` - Specifies the visual icon for the Freeze card in the UI.

*   **`ItemActionComponent`**:
    *   `_tags`: `enabled_in_world` - Indicates the action is available when the item is in the game world.
    *   `action_id`: `FREEZE` - The unique identifier for this spell action.

### Transform (`InheritTransformComponent`)

This component manages the positioning and orientation of the card when it's held by the player.

*   **`_tags`**: `enabled_in_world,enabled_in_hand` - The component is active when the item is in the world and being held.
*   **`Transform`**:
    *   `position.x`: `8` - Offset on the X-axis.
    *   `position.y`: `0` - Offset on the Y-axis.

### Particle Effects (`SpriteParticleEmitterComponent`)

This component defines the visual particles emitted when the Freeze card is identified and held.

*   **`_tags`**: `enabled_in_hand,item_identified` - Particles are active when the card is held and its identity is known.
*   **`sprite_file`**: `data/particles/snowflake_$[1-2].xml` - Uses snowflake particle sprites.
*   **`delay`**: `0` - Particles start emitting immediately.
*   **`lifetime`**: `10` - Duration of each particle.
*   **`color`**: `r="1" g="1" b="1" a="1"` - Initial white color.
*   **`color_change`**: `a="-0.5"` - Alpha (transparency) decreases over time.
*   **`gravity`**: `y="10"` - Particles are affected by gravity.
*   **`emission_interval_min_frames`**: `10`
*   **`emission_interval_max_frames`**: `20` - Controls the rate of particle emission.
*   **`count_min`**: `1`
*   **`count_max`**: `1` - Emits one particle at a time.
*   **`randomize_rotation`**: `min="-3.1415" max="3.1415"` - Randomizes particle rotation.
*   **`randomize_angular_velocity`**: `min="-1" max="1"` - Randomizes particle spinning.
*   **`randomize_position`**: `min_x="-2" max_x="2" min_y="-2" max_y="2"` - Randomizes particle spawn location around the card.
*   **`randomize_velocity`**: `min_y="0" max_y="2" min_x="-2" max_x="2"` - Randomizes particle initial velocity.

### Light Component (`LightComponent`)

This component adds a light source when the card is identified and held.

*   **`_tags`**: `enabled_in_hand,item_identified` - Light is active when the card is held and identified.
*   **`_enabled`**: `1` - The light component is enabled.
*   **`radius`**: `30` - The range of the light.
*   **`fade_out_time`**: `1.5` - How long the light takes to fade.
*   **`r`, `g`, `b`**: `10`, `30`, `60` - Defines the cool blue color of the light.