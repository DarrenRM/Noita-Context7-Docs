---
title: Icethrower Custom Card
category: entities
---

# Icethrower Custom Card

This document details the `icethrower.xml` entity, representing a custom wand card in Noita.

## Base Entity

The core of this custom card is built upon `base_custom_card.xml`.

### Key Components:

*   **`SpriteComponent`**: Defines the visual representation of the card in the UI.
    *   `image_file`: `data/ui_gfx/gun_actions/icethrower.png` - Specifies the sprite used for the Icethrower card.
*   **`ItemActionComponent`**: Assigns an action ID to the card, making it functional in the game.
    *   `action_id`: `ICETHROWER` - The unique identifier for this wand's action.

## Visual and Particle Effects

This section describes the visual flair associated with the Icethrower when held.

### Key Components:

*   **`SpriteParticleEmitterComponent`**: Manages the emission of snowflake-like particles.
    *   `sprite_file`: `data/particles/snowflake_$[1-2].xml` - Uses snowflake particle sprites.
    *   `lifetime`: `10` - Duration of each particle.
    *   `color`: `r="1" g="1" b="1" a="1"` - White color.
    *   `color_change`: `a="-0.5"` - Fades out over time.
    *   `gravity`: `y="10"` - Particles are affected by gravity.
    *   `emission_interval_min_frames`/`max_frames`: `10`/`20` - Controls the rate of particle emission.
    *   `count_min`/`max`: `1`/`1` - Emits one particle at a time.
    *   `randomize_rotation`, `randomize_angular_velocity`, `randomize_position`, `randomize_velocity`: Various parameters to give particles a natural, scattered appearance.

*   **`ParticleEmitterComponent`**: Emits smaller, cosmetic particles for additional visual feedback.
    *   `emitted_material_name`: `spark_blue` - Uses blue sparks.
    *   `x_vel_min`/`max`, `y_vel_min`/`max`: `-2` to `2` for X, `-20` to `-10` for Y - Gives particles an upward, outward trajectory.
    *   `count_min`/`max`: `1`/`2` - Emits 1-2 particles per burst.
    *   `lifetime_min`/`max`: `0.4`/`0.6` - Short lifespan for these particles.
    *   `emission_interval_min_frames`/`max_frames`: `5`/`15` - Controls the frequency of these cosmetic bursts.
    *   `is_emitting`: `1` - Ensures particles are continuously emitted when the item is identified.

*   **`LightComponent`**: Adds a subtle glow effect when the card is held.
    *   `radius`: `30` - The range of the light.
    *   `fade_out_time`: `1.5` - How long the light fades out.
    *   `r`, `g`, `b`: `10`, `30`, `60` - A cool blueish light.