---
title: Electric Charge Custom Card
category: entities
---

# Electric Charge Custom Card

This document describes the `electric_charge.xml` entity, which defines a custom card in Noita that imbues the player with electrical properties.

## Key Components

### Base Entity (`base_custom_card.xml`)

This is the foundational entity for custom cards, providing basic functionality and structure.

*   **`SpriteComponent`**:
    *   `image_file`: `data/ui_gfx/gun_actions/electric_charge.png` - Specifies the visual representation of the card on the UI.
*   **`ItemActionComponent`**:
    *   `_tags`: `enabled_in_world` - Indicates the action is available when the player is in the game world.
    *   `action_id`: `ELECTRIC_CHARGE` - A unique identifier for this specific card action.

### Electricity Properties (`base_electricity.xml`)

This base entity likely provides the core electrical effects and behaviors associated with the card. Specific details would be found within `base_electricity.xml` itself.

### Visual Effects (`LightComponent`)

This component adds a visual glow effect when the card is held or identified.

*   `_tags`: `enabled_in_hand,item_identified` - The light is active when the item is in hand and has been identified.
*   `_enabled`: `1` - The light component is active.
*   `radius`: `40` - The radius of the light effect.
*   `fade_out_time`: `1.5` - The time it takes for the light to fade out.
*   `r`, `g`, `b`: `20`, `40`, `150` - Defines the color of the light (a bluish hue).

### Particle Effects (`Base file="data/entities/particles/water_electrocution.xml"`)

This indicates that the `electric_charge.xml` entity inherits particle effects from `water_electrocution.xml`. This likely means the card will trigger electrical particle effects, possibly related to water interactions.

---