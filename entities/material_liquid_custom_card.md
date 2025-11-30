---
title: Material Liquid Custom Card
category: entities
---

# Material Liquid Custom Card

This document describes the `material_liquid.xml` entity, which defines a custom spell card in Noita that allows the player to pick up and shoot liquids.

## Key Components

### Base Entity

*   **`base_custom_card.xml`**: Inherits core functionality for custom spell cards.
    *   **`SpriteComponent`**:
        *   `image_file`: `data/ui_gfx/gun_actions/material_liquid.png` - Specifies the visual icon for this card in the UI.
    *   **`ItemActionComponent`**:
        *   `action_id`: `MATERIAL_LIQUID` - Identifies the specific action this card performs.
        *   `_tags`: `enabled_in_world` - Ensures the card is active when in the game world.

### Transform Component

*   **`InheritTransformComponent`**:
    *   `_tags`: `enabled_in_world,enabled_in_hand` - Makes the card active when in the world and when held by the player.
    *   `parent_hotspot_tag`: `shoot_pos` - Defines the origin point for actions related to shooting.

### Material Sucker Component

*   **`MaterialSuckerComponent`**:
    *   `_tags`: `enabled_in_world` - Activates the material sucking functionality in the game world.
    *   `set_projectile_to_liquid`: `1` - This is the core attribute that enables the projectile fired by this card to be a liquid.