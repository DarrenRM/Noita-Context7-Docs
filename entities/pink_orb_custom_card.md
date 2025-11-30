---
title: Pink Orb Custom Card
category: entities
---

# Pink Orb Custom Card

This document describes the `pink_orb.xml` entity, which defines a custom spell card in Noita.

## Entity Definition

The `pink_orb.xml` entity inherits its core functionality from `base_custom_card.xml` and `base_laser.xml`.

### Base Custom Card (`base_custom_card.xml`)

This section defines the visual and functional aspects of the spell card when it appears as an item.

*   **`SpriteComponent`**:
    *   `image_file`: Specifies the UI texture for the spell card, `data/ui_gfx/gun_actions/pink_orb.png`.
*   **`ItemActionComponent`**:
    *   `_tags`: Set to `"enabled_in_world"`, meaning the card can be picked up and used in the game world.
    *   `action_id`: Identifies this card as `"PINK_ORB"`.

### Base Laser (`base_laser.xml`)

This section defines the particle effects associated with the spell when it's cast.

*   **`SpriteParticleEmitterComponent`**:
    *   `sprite_file`: The particle sprite used for a shimmering effect, `data/particles/shine_pink.xml`.
    *   `emission_interval_min_frames`: Minimum frames between particle emissions.
    *   `emission_interval_max_frames`: Maximum frames between particle emissions.
*   **`ParticleEmitterComponent`**:
    *   `emitted_material_name`: The material of the particles emitted, `"plasma_fading_pink"`.