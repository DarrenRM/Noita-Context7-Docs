---
title: Tentacle Timer Custom Card
category: data/entities
---

---

# Tentacle Timer Custom Card

This document describes the `tentacle_timer.xml` entity, which represents a custom card in Noita. This card, when used, likely triggers a visual effect or gameplay mechanic related to tentacles.

## Key Components

### Base Entity (`<Base>`)

This is the foundational element for custom cards, providing essential properties.

*   **`file="data/entities/base_custom_card.xml"`**: Inherits core functionality from the base custom card entity.
*   **`<SpriteComponent>`**: Defines the visual representation of the card.
    *   **`image_file="data/ui_gfx/gun_actions/tentacle_timer.png"`**: Specifies the image used for the card's icon.
*   **`<ItemActionComponent>`**: Handles the card's in-game action.
    *   **`_tags="enabled_in_world"`**: Ensures the action is available when the item is in the game world.
    *   **`action_id="TENTACLE_TIMER"`**: A unique identifier for this specific action.

### Transform Component (`<InheritTransformComponent>`)

This component dictates how the card's visual elements are positioned relative to the player's hand.

*   **`_tags="enabled_in_world,enabled_in_hand"`**: Makes the transform active when the item is in the world and held by the player.
*   **`parent_hotspot_tag="shoot_pos"`**: Aligns the card's position with the "shoot\_pos" hotspot of its parent (likely the player's hand or weapon).

### Particle Emitter (`<SpriteParticleEmitterComponent>`)

This component is responsible for generating visual particle effects when the card is in hand.

*   **`_tags="enabled_in_hand,item_identified"`**: Activates the particle emitter when the item is held and identified.
*   **`sprite_file="data/particles/creepy.xml"`**: Links to a particle definition file, suggesting a "creepy" visual style.
*   **`delay="0"`**: Particles are emitted immediately.
*   **`lifetime="0"`**: Particles have no inherent lifetime, likely managed by other properties.
*   **`color.r="1" color.g="1" color.b="1" color.a="0.4"`**: Initial color is white with some transparency.
*   **`color_change.a="-1"`**: Alpha (transparency) decreases over time.
*   **`emission_interval_min_frames="3"`**, **`emission_interval_max_frames="4"`**: Particles are emitted every 3-4 frames.
*   **`count_min="1"`**, **`count_max="1"`**: Emits one particle per emission interval.
*   **Randomization Properties**: A significant number of properties are randomized to create a dynamic and varied particle effect, including:
    *   `randomize_rotation`
    *   `randomize_angular_velocity`
    *   `randomize_position` (small offset)
    *   `randomize_velocity` (spread in X and Y directions)