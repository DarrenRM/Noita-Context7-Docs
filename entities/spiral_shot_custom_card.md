---
title: Spiral Shot Custom Card
category: entities
---

# Spiral Shot Custom Card

This document describes the `spiral_shot.xml` entity, which defines a custom spell card in Noita.

## Core Functionality

The `Spiral Shot` custom card is designed to be a projectile that spirals outwards.

### Key Components

*   **`Base file="data/entities/base_custom_card.xml"`**: Inherits core functionality for custom spell cards.
    *   **`SpriteComponent`**: Defines the visual representation of the card in the UI.
        *   `image_file`: `data/ui_gfx/gun_actions/spiral_shot.png` - Specifies the sprite for the card.
    *   **`ItemActionComponent`**: Links the card to a specific in-game action.
        *   `_tags="enabled_in_world"`: Ensures the card is usable during gameplay.
        *   `action_id="SPIRAL_SHOT"`: Identifies the unique action associated with this card.

*   **`Base file="data/entities/misc/custom_cards/base_laser.xml"`**: Inherits visual effects and particle emission properties from a base laser entity.
    *   **`SpriteParticleEmitterComponent`**: Adds a visual particle effect.
        *   `sprite_file="data/particles/shine_blue.xml"`: Uses a blue shine particle for visual flair.
    *   **`ParticleEmitterComponent`**: Configures the material of emitted particles.
        *   `emitted_material_name="spark_blue"`: Sets the emitted particles to be blue sparks.