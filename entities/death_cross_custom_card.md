---
title: Death Cross Custom Card
category: entities
---

# Death Cross Custom Card

This document describes the `death_cross.xml` entity, which defines a custom spell card in Noita.

## Entity Definition

The `death_cross.xml` entity is composed of two `Base` components, inheriting functionality from `base_custom_card.xml` and `base_laser.xml`.

### `base_custom_card.xml` Components

*   **SpriteComponent**:
    *   `image_file`: `data/ui_gfx/gun_actions/death_cross.png` - Specifies the visual representation of the card on the UI.
*   **ItemActionComponent**:
    *   `_tags`: `enabled_in_world` - Indicates the card is usable during gameplay.
    *   `action_id`: `DEATH_CROSS` - A unique identifier for this spell action.

### `base_laser.xml` Components

*   **SpriteParticleEmitterComponent**:
    *   `sprite_file`: `data/particles/shine_blue.xml` - Defines the particle effect used for visual flair.
    *   `emission_interval_min_frames`: `35` - Minimum frames between particle emissions.
    *   `emission_interval_max_frames`: `45` - Maximum frames between particle emissions.
*   **ParticleEmitterComponent**:
    *   `emitted_material_name`: `plasma_fading` - Specifies the material of the particles emitted, contributing to the spell's visual and potentially functional effects.