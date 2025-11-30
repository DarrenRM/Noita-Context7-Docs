---
title: Custom Card - Circle Shot A
category: entities
---

# Custom Card - Circle Shot A

This document describes the `circleshot_a.xml` entity, which defines a custom spell card in Noita.

## Entity Structure

The `circleshot_a.xml` entity is composed of two `Base` elements, inheriting functionality from:

*   `data/entities/base_custom_card.xml`: Provides the fundamental structure for custom spell cards.
*   `data/entities/misc/custom_cards/base_laser.xml`: Inherits properties related to laser-like effects.

## Key Components and Attributes

### Base Custom Card (`data/entities/base_custom_card.xml`)

*   **`SpriteComponent`**:
    *   `image_file`: Specifies the visual representation of the card in the UI. In this case, it uses `data/ui_gfx/gun_actions/phantomshot_a.png`.
*   **`ItemActionComponent`**:
    *   `_tags`: Marks the item as `enabled_in_world`, meaning it can be found and used during gameplay.
    *   `action_id`: Assigns a unique identifier, `CIRCLESHOT_A`, to this specific spell action.

### Base Laser (`data/entities/misc/custom_cards/base_laser.xml`)

*   **`SpriteParticleEmitterComponent`**:
    *   `sprite_file`: Defines the particle effect used, referencing `data/particles/shine_green.xml` for a green shining effect.
    *   `emission_interval_min_frames`: Sets the minimum delay between particle emissions (35 frames).
    *   `emission_interval_max_frames`: Sets the maximum delay between particle emissions (45 frames).

This configuration suggests that the "Circle Shot A" custom card will visually appear as "phantomshot_a.png" in the UI and will have a green particle effect associated with its use, likely related to a laser-like projectile.