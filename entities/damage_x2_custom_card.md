---
title: Damage x2 Custom Card
category: entities
---

# Damage x2 Custom Card

This entity defines a custom card that doubles the damage of a spell.

## Key Components

### Base Custom Card

This is the foundational element for custom cards, providing basic functionality and visual representation.

*   **`SpriteComponent`**:
    *   `image_file`: `data/ui_gfx/gun_actions/damage_x2.png` - Specifies the visual icon for this card in the UI.
*   **`ItemActionComponent`**:
    *   `_tags`: `enabled_in_world` - Indicates this action is available when the player is in the game world.
    *   `action_id`: `DAMAGE_X2` - The unique identifier for this damage-doubling action.

### Base Damage Card

This component adds particle effects associated with the damage modification.

*   **`SpriteParticleEmitterComponent`**:
    *   `sprite_file`: `data/particles/tinyspark_02.xml` - Defines the particle effect to be emitted, likely a visual indicator of the damage boost.