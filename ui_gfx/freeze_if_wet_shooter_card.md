---
title: Freeze If Wet Shooter Card
category: data/entities
---

# Freeze If Wet Shooter Card

This entity defines a custom wand card in Noita that applies a freeze effect to enemies when the player is wet.

## Key Components

### Base Custom Card
This component inherits the fundamental properties of a custom wand card.

*   **`image_file`**: `data/ui_gfx/gun_actions/freeze.png` - Specifies the visual icon for this card in the UI.
*   **`action_id`**: `FREEZE_IF_WET_SHOOTER` - A unique identifier for this card's action.

### Inherit Transform Component
This component handles the positioning and transformation of the card when held by the player.

*   **`position.x`**: `8` - Offset on the x-axis.
*   **`position.y`**: `0` - Offset on the y-axis.

### Sprite Particle Emitter Component
This component generates visual particle effects associated with the card.

*   **`sprite_file`**: `data/particles/snowflake_$[1-2].xml` - Uses snowflake particle sprites for visual flair.
*   **`delay`**: `0` - Particles are emitted immediately.
*   **`lifetime`**: `10` - Duration of each particle.
*   **`color`**: `r="1" g="1" b="1" a="1"` - White, opaque color.
*   **`color_change`**: `a="-0.5"` - Particles fade out over their lifetime.
*   **`gravity`**: `y="10"` - Particles are affected by gravity.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `10` / `20` - Controls the rate of particle emission.
*   **`count_min` / `count_max`**: `1` / `1` - Emits a single particle per emission cycle.
*   **`randomize_rotation`**: `-3.1415` to `3.1415` - Particles have random initial rotations.
*   **`randomize_angular_velocity`**: `-1` to `1` - Particles have random spinning speeds.
*   **`randomize_position`**: Offsets particles slightly around the emitter.
*   **`randomize_velocity`**: Particles have a slight upward and outward velocity.

### Light Component
This component adds a light source when the card is held.

*   **`radius`**: `30` - The range of the light.
*   **`fade_out_time`**: `1.5` - How long the light takes to fade.
*   **`r`, `g`, `b`**: `10`, `30`, `60` - A cool blueish light color.

### Shot Effect Component
This is the core component that defines the card's unique behavior.

*   **`condition_status`**: `WET` - The effect is triggered only when the player is wet.
*   **`extra_modifier`**: `game_effect_freeze` - Applies the "freeze" game effect to the target.