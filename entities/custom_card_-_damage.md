---
title: Custom Card - Damage
category: entities
---

# Custom Card - Damage

This entity defines a custom card in Noita that applies a damage effect. It inherits its base functionality from `base_custom_card.xml` and `base_damage.xml`.

## Key Components

### Base Entity (`base_custom_card.xml`)

This component provides the fundamental structure for a custom card.

*   **SpriteComponent**:
    *   `image_file`: Specifies the visual representation of the card in the UI.
        *   `data/ui_gfx/gun_actions/damage.png`

*   **ItemActionComponent**:
    *   `_tags`: Defines when the action is available.
        *   `enabled_in_world`: The action is available when the player is in the game world.
    *   `action_id`: A unique identifier for this action.
        *   `DAMAGE`

### Base Damage (`base_damage.xml`)

This component likely contains the specific logic for applying damage when this custom card is used. The exact details of damage application (amount, type, etc.) would be defined within this inherited XML.