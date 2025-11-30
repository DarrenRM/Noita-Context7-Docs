---
title: Energy Shield Custom Card
category: entities
---

# Energy Shield Custom Card

This document describes the `energy_shield_old.xml` entity, which defines a custom card in Noita that grants the player an energy shield.

## Key Components

### Base Entity

*   **`Base file="data/entities/base_custom_card.xml"`**: Inherits core functionality for custom cards.
    *   **`SpriteComponent`**: Defines the UI icon for the card.
        *   `image_file="data/ui_gfx/gun_actions/energy_shield.png"`: The visual representation of the card in the UI.

### Item Action

*   **`ItemActionComponent`**: Specifies the action associated with this card.
    *   `action_id="ENERGY_SHIELD"`: Identifies the specific action this card performs.
    *   `_tags="enabled_in_world"`: Indicates the card is active when in the game world.

### Transform

*   **`InheritTransformComponent`**: Manages the positioning of the item when held by the player.
    *   `use_root_parent="1"`: The item's transform is relative to the player's root.
    *   **`Transform`**: Defines the offset from the player's hand.
        *   `position.x="0"`
        *   `position.y="-4"`

### Energy Shield Logic

*   **`EnergyShieldComponent`**: The core component responsible for the energy shield's behavior.
    *   `_tags="enabled_in_hand,item_identified"`: The shield is active when the item is held and identified.
    *   `recharge_speed="0.25"`: How quickly the shield regenerates.
    *   `radius="16.0"`: The size of the shield's protective area.

### Visuals and Effects

*   **`SpriteAnimatorComponent`**: Handles animations for the item when held.
    *   `_tags="enabled_in_hand"`: Active when the item is in hand.

*   **`SpriteComponent`**: Defines the visual effect of the energy shield itself.
    *   `_tags="enabled_in_hand,character,item_identified"`: The shield's visual is active when held and identified.
    *   `image_file="data/particles/energy_shield_016.xml"`: Points to the particle effect definition for the shield.
    *   `additive="1"`: Enables additive blending for the sprite.
    *   `emissive="1"`: Makes the sprite emit light.

*   **`LightComponent`**: Adds a light source to the shield.
    *   `_tags="enabled_in_hand,item_identified"`: The light is active when the item is held and identified.
    *   `_enabled="1"`: The light component is initially enabled.
    *   `radius="80"`: The range of the light.
    *   `fade_out_time="1.5"`: How long it takes for the light to fade.
    *   `r="150"`, `g="190"`, `b="230"`: The RGB color of the light (a bluish hue).