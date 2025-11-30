---
title: Custom Card - Explosion
category: entities
---

# Custom Card - Explosion

This entity defines a custom spell card in Noita that, when cast, creates an explosion. It inherits functionality from `base_custom_card.xml` and `base_explosive.xml`.

## Key Components

### Base Custom Card (`base_custom_card.xml`)

This component defines the fundamental properties of a custom spell card.

*   **SpriteComponent**:
    *   `image_file`: `data/ui_gfx/gun_actions/explosion.png` - Specifies the visual representation of the card on the UI.
*   **ItemActionComponent**:
    *   `_tags`: `enabled_in_world` - Indicates the card is usable during gameplay.
    *   `action_id`: `EXPLOSION` - A unique identifier for this spell action.

### Base Explosive (`base_explosive.xml`)

This component provides the core explosion mechanics for the spell. While the specific attributes are not detailed here, it's responsible for defining the explosion's damage, radius, and any associated effects.