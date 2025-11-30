---
title: Custom Card - Random Damage
category: entities
---

# Custom Card - Random Damage

This entity defines a custom spell card in Noita that applies a random damage effect. It inherits functionality from `base_custom_card.xml` and `base_damage.xml`.

## Key Components

### Base Entity (`base_custom_card.xml`)

*   **SpriteComponent**: Defines the visual representation of the card in the game's UI.
    *   `image_file`: Specifies the texture used for the card's icon.

### Item Action Component (`ItemActionComponent`)

*   **action\_id**: Identifies the specific action this card performs.
    *   `DAMAGE_RANDOM`: This ID signifies the card's function to deal random damage.
*   `_tags`: Controls when the action is available.
    *   `enabled_in_world`: The card is usable when found in the game world.

### Base Damage Entity (`base_damage.xml`)

*   **SpriteParticleEmitterComponent**: Adds visual particle effects when the card is used.
    *   `sprite_file`: Points to the particle effect definition (e.g., `data/particles/tinyspark_02.xml`).