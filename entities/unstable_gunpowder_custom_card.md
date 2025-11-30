---
title: Unstable Gunpowder Custom Card
category: entities
---

# Unstable Gunpowder Custom Card

This document describes the `unstable_gunpowder.xml` entity, which represents a custom card in Noita. This card, when used, applies the "Unstable Gunpowder" effect.

## Key Components

### Base Entity (`base_custom_card.xml`)

This is the foundational entity for custom cards, providing core functionality.

*   **`SpriteComponent`**: Defines the visual representation of the card in the UI.
    *   `image_file`: `data/ui_gfx/gun_actions/unstable_gunpowder.png` - Specifies the texture for the card's icon.

*   **`ItemActionComponent`**: Handles the action associated with the card.
    *   `_tags`: `enabled_in_world` - Indicates the card is usable in the game world.
    *   `action_id`: `UNSTABLE_GUNPOWDER` - The unique identifier for this card's action.

### Inherited Base (`base_high_explosive.xml`)

This entity inherits properties from `base_high_explosive.xml`, suggesting it shares characteristics with other high-explosive effects.

### Light Component

This component adds a visual light effect when the item is held or identified.

*   `_tags`: `enabled_in_hand,item_identified` - The light is active when the item is in hand or its properties are known.
*   `_enabled`: `1` - The light component is active.
*   `radius`: `20` - The radius of the light effect.
*   `fade_out_time`: `1.5` - The time it takes for the light to fade out.
*   `r`, `g`, `b`: `80`, `60`, `10` - The RGB color values of the light, giving it a warm, orange-ish hue.