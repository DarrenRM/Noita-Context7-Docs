---
title: Explosion Light Custom Card
category: entities
---

# Explosion Light Custom Card

This entity defines a custom spell card in Noita that, when cast, creates a light-based explosion. It inherits functionality from `base_custom_card.xml` and `base_explosive.xml`.

## Key Components

### Base Custom Card (`base_custom_card.xml`)

This component defines the fundamental properties of a custom spell card.

*   **`SpriteComponent`**:
    *   `image_file`: `data/ui_gfx/gun_actions/explosion_light.png` - Specifies the visual representation of the card on the UI.

*   **`ItemActionComponent`**:
    *   `_tags`: `enabled_in_world` - Indicates that this action is available for use within the game world.
    *   `action_id`: `EXPLOSION_LIGHT` - A unique identifier for this specific spell action.

### Base Explosive (`base_explosive.xml`)

This component provides the core logic for explosive effects. While not explicitly detailed here, it's responsible for the actual explosion mechanics when this card is used.