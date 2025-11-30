---
title: Iceball Custom Card
category: entities
---

# Iceball Custom Card

This document describes the `iceball.xml` entity, which defines a custom spell card in Noita.

## Entity Definition

The `iceball.xml` entity inherits from `base_custom_card.xml` and `base_ice.xml` to define its properties.

### Base Custom Card Properties

*   **Sprite Component**:
    *   `image_file`: `data/ui_gfx/gun_actions/iceball.png` - This specifies the visual representation of the spell card on the UI.
*   **Item Action Component**:
    *   `_tags`: `enabled_in_world` - Indicates that this action is available when the player is in the game world.
    *   `action_id`: `ICEBALL` - A unique identifier for this spell action.

### Base Ice Properties

This entity inherits from `base_ice.xml`, which likely defines the core mechanics and effects related to ice spells. This would include projectile behavior, damage types, and any status effects associated with ice.