---
title: Charm Custom Card Entity
category: entities
---

# Charm Custom Card Entity

This document describes the `charm.xml` entity, which defines a custom card in Noita. This card, when picked up, applies a "charm" effect.

## Key Components

### Base Custom Card (`<Base file="data/entities/base_custom_card.xml">`)

This is the foundational component for all custom cards.

*   **`SpriteComponent`**:
    *   `image_file`: Specifies the visual representation of the card in the game's UI.
        *   `data/ui_gfx/gun_actions/charm.png`

*   **`ItemActionComponent`**:
    *   `action_id`: Defines the unique identifier for the action this card performs.
        *   `CHARM`

### Transform (`<InheritTransformComponent>`)

This component dictates the positioning of the card when it's held by the player.

*   **`Transform`**:
    *   `position.x`: Horizontal offset from the player's hand.
        *   `8`
    *   `position.y`: Vertical offset from the player's hand.
        *   `0`

### Particle Effects (`<SpriteParticleEmitterComponent>`)

This component generates visual particle effects associated with the charm card when it's held and identified.

*   **`sprite_file`**: References the particle definition.
    *   `data/particles/charm.xml`
*   **`delay`**: Initial delay before particles start emitting.
    *   `0`
*   **`lifetime`**: Duration of the particle effect in seconds.
    *   `1.5`
*   **`color`**: Initial color of the particles (RGBA).
    *   `r="1" g="1" b="1" a="1"` (White)
*   **`color_change`**: How the color changes over the particle's lifetime.
    *   `a="-1"` (Alpha fades out)
*   **`gravity`**: The gravitational pull on the particles.
    *   `y="10"`
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: Controls the rate of particle emission.
    *   `min="22"`, `max="30"`
*   **`count_min` / `count_max`**: The number of particles emitted per interval.
    *   `min="1"`, `max="1"`
*   **Randomization Parameters**: These attributes introduce variation in particle behavior:
    *   `randomize_rotation`: Randomizes the initial rotation of particles.
    *   `randomize_angular_velocity`: Randomizes the rotational speed of particles.
    *   `randomize_position`: Randomizes the emission position within a small area.
    *   `randomize_velocity`: Randomizes the initial velocity of particles in X and Y directions.