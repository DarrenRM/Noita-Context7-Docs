---
title: Levitation Projectile Card
category: entities
---

# Levitation Projectile Card

This document describes the `levitation_projectile.xml` entity, which defines a custom spell card in Noita that grants the player a levitation effect.

## Key Components

### Base Entity (`<Base>`)

This is the foundational element for custom spell cards.

*   **`file="data/entities/base_custom_card.xml"`**: Inherits core functionality for custom cards.
*   **`<SpriteComponent>`**: Defines the visual representation of the card in the UI.
    *   **`image_file="data/ui_gfx/gun_actions/levitation_projectile.png"`**: Specifies the texture used for the card's icon.
*   **`<ItemActionComponent>`**: Links the card to a specific game action.
    *   **`action_id="LEVITATION_PROJECTILE"`**: Identifies the action this card triggers.

### Inheritance and Positioning (`<InheritTransformComponent>`)

This component dictates how the card's visual elements are positioned relative to the player's hand.

*   **`_tags="enabled_in_world,enabled_in_hand"`**: Ensures this component is active when the card is in the world or held by the player.
*   **`<Transform>`**: Defines the offset from the parent entity.
    *   **`position.x="8"`**: Offsets the card 8 units to the right.
    *   **`position.y="0"`**: No vertical offset.

### Particle Effects (`<SpriteParticleEmitterComponent>`)

This component generates visual particle effects associated with the card when it's identified or in hand.

*   **`_tags="enabled_in_hand,item_identified"`**: Activates the particle emitter under specific conditions.
*   **`sprite_file="data/particles/shine_confusion.xml"`**: Uses a predefined particle effect.
*   **`delay="0"`**: Starts emitting immediately.
*   **`lifetime="0"`**: Particles have no inherent lifetime set by the emitter.
*   **`color.r="1" color.g="1" color.b="1" color.a="1"`**: Initial white color.
*   **`color_change.a="-1"`**: Alpha value decreases over time.
*   **`gravity.y="10"`**: Particles are affected by gravity pulling them downwards.
*   **`velocity_slowdown="0.5"`**: Particles lose half their velocity over time.
*   **`emission_interval_min_frames="24"` and `emission_interval_max_frames="45"`**: Controls the timing between particle emissions.
*   **`count_min="1"` and `count_max="2"`**: Emits 1 to 2 particles per emission cycle.
*   **Randomization**: Various `randomize_` attributes control the spread and initial properties of emitted particles, including rotation, angular velocity, position, and velocity.

### Lighting Effects (`<LightComponent>`)

This component adds a light source when the card is in hand and identified.

*   **`_tags="enabled_in_hand,item_identified"`**: Activates the light under specific conditions.
*   **`_enabled="1"`**: Ensures the light is active.
*   **`radius="30"`**: The range of the light.
*   **`fade_out_time="1.5"`**: How long the light takes to fade.
*   **`r="80" g="10" b="80"`**: Sets the light color to a purplish hue.