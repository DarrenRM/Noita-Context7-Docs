---
title: Teleport Projectile Custom Card
category: entities
---

# Teleport Projectile Custom Card

This document describes the `teleport_projectile.xml` entity, which defines a custom card in Noita that grants the player the "Teleport Projectile" action.

## Entity Definition

The core of this entity is the `<Entity>` tag.

### Base Components

This entity inherits from `base_custom_card.xml`, providing fundamental properties for custom cards.

*   **`<Base>`**:
    *   **`file="data/entities/base_custom_card.xml"`**: Specifies the base entity file.
    *   **`<SpriteComponent>`**:
        *   **`image_file="data/ui_gfx/gun_actions/teleport_projectile.png"`**: Defines the visual icon for this card in the UI.
    *   **`<ItemActionComponent>`**:
        *   **`_tags="enabled_in_world"`**: Ensures this action is available when the card is in the game world.
        *   **`action_id="TELEPORT_PROJECTILE"`**: Assigns a unique identifier to this specific action.

### Transform and Visuals

These components define how the card appears and behaves when held.

*   **`<InheritTransformComponent>`**:
    *   **`_tags="enabled_in_world,enabled_in_hand"`**: Applies the transform when the card is in the world or held by the player.
    *   **`<Transform>`**:
        *   **`position.x="8"`**: Offsets the card's position horizontally.
        *   **`position.y="0"`**: Offsets the card's position vertically.

*   **`<SpriteParticleEmitterComponent>`**: This component creates visual particle effects when the item is identified and held.
    *   **`_tags="enabled_in_hand,item_identified"`**: Activates the emitter when the item is held and identified.
    *   **`sprite_file="data/particles/shine_02.xml"`**: Uses a predefined particle sprite.
    *   **`delay="0"`**: Starts emitting immediately.
    *   **`lifetime="2"`**: Particles last for 2 seconds.
    *   **`color.r="1" color.g="1" color.b="1" color.a="1"`**: Initial white color.
    *   **`color_change.a="-1"`**: Alpha (transparency) decreases over time.
    *   **`gravity.y="10"`**: Particles are affected by gravity.
    *   **`emission_interval_min_frames="24"`**, **`emission_interval_max_frames="45"`**: Controls the timing between particle emissions.
    *   **`count_min="1"`**, **`count_max="2"`**: Emits 1 to 2 particles per emission.
    *   **Randomization**: Various `randomize_` attributes control the spread and initial velocity of particles, creating a dynamic visual effect.

*   **`<LightComponent>`**: Adds a light source when the item is identified and held.
    *   **`_tags="enabled_in_hand,item_identified"`**: Activates the light when the item is held and identified.
    *   **`_enabled="1"`**: Ensures the light is active.
    *   **`radius="30"`**: The range of the light.
    *   **`fade_out_time="1.5"`**: How long the light takes to fade.
    *   **`r="20" g="80" b="80"`**: Sets the light color to a teal hue.