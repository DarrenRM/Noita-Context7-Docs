---
title: Tentacle Custom Card
category: data/entities
---

# Tentacle Custom Card

This document describes the `tentacle.xml` entity, which defines a custom card in Noita. This card, when used, visually represents a "tentacle" effect.

## Key Components

### Base Entity (`<Base>`)

This is the foundational element for custom cards, providing essential properties.

*   **`file="data/entities/base_custom_card.xml"`**: Inherits core functionality from the base custom card definition.
*   **`<SpriteComponent>`**: Defines the visual representation of the card in the UI.
    *   **`image_file="data/ui_gfx/gun_actions/tentacle.png"`**: Specifies the image used for the card's icon.
*   **`<ItemActionComponent>`**: Links the card to a specific in-game action.
    *   **`action_id="TENTACLE"`**: Identifies the action triggered when this card is used.
    *   **`_tags="enabled_in_world"`**: Ensures the action is available when the card is in the game world.

### Transform Component (`<InheritTransformComponent>`)

This component dictates how the card's visual elements are positioned relative to the player's hand.

*   **`parent_hotspot_tag="shoot_pos"`**: Aligns the card's visual effects with the "shoot position" of the player's wand.
*   **`_tags="enabled_in_world,enabled_in_hand"`**: Makes this transform active when the card is in the world or held in hand.

### Particle Emitter (`<SpriteParticleEmitterComponent>`)

This component generates visual particle effects when the card is held.

*   **`_tags="enabled_in_hand,item_identified"`**: Activates the particle effect when the item is held and identified.
*   **`sprite_file="data/particles/creepy.xml"`**: Specifies the particle effect definition to use (likely a "creepy" visual style).
*   **`delay="0"`**, **`lifetime="0"`**: Indicates the particles are emitted continuously without a specific duration.
*   **`render_back="1"`**: Renders the particles behind other elements.
*   **`color.r="1" color.g="1" color.b="1" color.a="0.4"`**: Sets the initial color to white with some transparency.
*   **`color_change.a="-1"`**: The alpha (transparency) of the particles decreases over time.
*   **`emission_interval_min_frames="3"`**, **`emission_interval_max_frames="4"`**: Controls the rate of particle emission.
*   **`count_min="1" count_max="1"`**: Emits one particle at a time.
*   **Randomization Parameters**: A series of `randomize_` attributes control the variation in particle properties such as:
    *   **`rotation`**: Initial orientation.
    *   **`angular_velocity`**: How fast particles spin.
    *   **`position`**: Where particles spawn relative to the hotspot.
    *   **`velocity`**: Initial speed and direction.