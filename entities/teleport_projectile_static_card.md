---
title: Teleport Projectile Static Card
category: entities
---

# Teleport Projectile Static Card

This document details the `teleport_projectile_static.xml` entity, which defines a custom wand card in Noita. This card, when equipped, grants the player the ability to cast a projectile that teleports the player to its location.

## Key Components

### Base Entity (`<Base>`)

This is the foundational component for custom wand cards.

*   **`file="data/entities/base_custom_card.xml"`**: Inherits core functionality from the base custom card entity.
*   **`<SpriteComponent>`**: Defines the visual representation of the card in the UI.
    *   **`image_file="data/ui_gfx/gun_actions/teleport_projectile_static.png"`**: Specifies the image used for the card's icon.
*   **`<ItemActionComponent>`**: Links the card to a specific in-game action.
    *   **`action_id="TELEPORT_PROJECTILE_STATIC"`**: Identifies the unique action this card performs.
    *   **`_tags="enabled_in_world"`**: Ensures this action is available when the card is in the game world.

### Transform (`<InheritTransformComponent>`)

This component dictates the positioning of the card's visual elements when held.

*   **`_tags="enabled_in_world,enabled_in_hand"`**: The transform is active when the card is in the world and being held.
*   **`<Transform>`**: Defines the relative position.
    *   **`position.x="8"`**: Offsets the card 8 units to the right.
    *   **`position.y="0"`**: No vertical offset.

### Particle Emitter (`<SpriteParticleEmitterComponent>`)

This component adds visual flair to the card when it's identified and held.

*   **`_tags="enabled_in_hand,item_identified"`**: Particles are emitted when the item is held and identified.
*   **`sprite_file="data/particles/shine_02.xml"`**: Uses a predefined "shine" particle effect.
*   **`delay="0"`**: Particles start emitting immediately.
*   **`lifetime="2"`**: Particles last for 2 seconds.
*   **`color.r="1" color.g="1" color.b="1" color.a="1"`**: Initial white color.
*   **`color_change.a="-1"`**: Alpha (transparency) decreases over time.
*   **`gravity.y="10"`**: Particles are affected by gravity.
*   **`emission_interval_min_frames="24" emission_interval_max_frames="45"`**: Controls the timing between particle emissions.
*   **`count_min="1" count_max="2"`**: Emits 1 to 2 particles per emission.
*   **`randomize_rotation.min="-3.1415" randomize_rotation.max="3.1415"`**: Particles have random initial rotations.
*   **`randomize_position.min_x="-2" randomize_position.max_x="2"`**: Particles spawn within a small horizontal area.
*   **`randomize_velocity.min_y="0" randomize_velocity.max_y="10"`**: Particles have upward velocity.
*   **`randomize_velocity.min_x="-2" randomize_velocity.max_x="2"`**: Particles have random horizontal velocity.

### Light Component (`<LightComponent>`)

Adds a subtle light effect to the card when held and identified.

*   **`_tags="enabled_in_hand,item_identified"`**: Light is active when the item is held and identified.
*   **`_enabled="1"`**: The light component is enabled.
*   **`radius="30"`**: The radius of the light effect.
*   **`fade_out_time="1.5"`**: The time it takes for the light to fade out.
*   **`r="20" g="80" b="80"`**: Defines the greenish-blue color of the light.