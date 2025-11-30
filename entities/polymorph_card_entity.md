---
title: Polymorph Card Entity
category: entities
---

# Polymorph Card Entity

This document describes the `polymorph.xml` entity, which represents the Polymorph spell card in Noita. This card allows the player to transform into a different creature.

## Base Entity

The core of this entity is based on `base_custom_card.xml`, providing fundamental properties for a custom spell card.

### Key Components:

*   **`Base file="data/entities/base_custom_card.xml"`**: Inherits common properties of custom cards.
    *   **`SpriteComponent`**:
        *   `image_file="data/ui_gfx/gun_actions/polymorph.png"`: Defines the visual representation of the card in the UI.
    *   **`ItemActionComponent`**:
        *   `_tags="enabled_in_world"`: Makes the action available when the card is in the game world.
        *   `action_id="POLYMORPH"`: Assigns the unique identifier for the Polymorph action.

## Visual and Effect Components

These components define the visual effects and behavior of the Polymorph card when held or identified.

### Key Components:

*   **`InheritTransformComponent`**:
    *   `_tags="enabled_in_world,enabled_in_hand"`: Ensures this component is active when the card is in the world and held by the player.
    *   **`Transform`**:
        *   `position.x="8"`: Offsets the card's position horizontally.
        *   `position.y="0"`: Offsets the card's position vertically.

*   **`SpriteParticleEmitterComponent`**: Creates a visual particle effect when the card is held and identified.
    *   `_tags="enabled_in_hand,item_identified"`: Activates the particle effect under specific conditions.
    *   `sprite_file="data/particles/shine_03.xml"`: Specifies the particle sprite to use.
    *   `lifetime="2"`: Duration of the particle effect.
    *   `color.r="1" color.g="1" color.b="1" color.a="1"`: Initial white color.
    *   `color_change.a="-1"`: Fades out the alpha channel over time.
    *   `gravity.y="10"`: Applies a downward gravitational force to particles.
    *   `velocity_slowdown="0.5"`: Slows down particle velocity.
    *   `emission_interval_min_frames="10"` and `emission_interval_max_frames="20"`: Controls the timing between particle emissions.
    *   `count_min="1"` and `count_max="1"`: Emits one particle per emission cycle.
    *   `randomize_rotation.min="-3.1415"` and `randomize_rotation.max="3.1415"`: Randomizes particle rotation.
    *   `randomize_angular_velocity.min="-15"` and `randomize_angular_velocity.max="15"`: Randomizes particle angular velocity.
    *   `randomize_velocity.min_y="0"` and `randomize_velocity.max_y="2"`: Randomizes upward particle velocity.
    *   `randomize_velocity.min_x="-2"` and `randomize_velocity.max_x="2"`: Randomizes horizontal particle velocity.

*   **`LightComponent`**: Adds a light source when the card is held and identified.
    *   `_tags="enabled_in_hand,item_identified"`: Activates the light under specific conditions.
    *   `_enabled="1"`: Ensures the light component is active.
    *   `radius="30"`: The radius of the light.
    *   `fade_out_time="1.5"`: How long the light takes to fade out.
    *   `r="10" g="30" b="60"`: Sets the light color to a bluish hue.