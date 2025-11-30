---
title: Worm Rain Custom Card
category: entities
---

# Worm Rain Custom Card

This document details the `worm_rain.xml` entity, which defines a custom card in Noita that triggers a "worm rain" effect.

## Entity Definition

The core of this entity is a custom card, inheriting from `base_custom_card.xml`.

### Base Components

*   **`Base file="data/entities/base_custom_card.xml"`**: Inherits fundamental properties of a custom card.
    *   **`SpriteComponent`**:
        *   `image_file="data/ui_gfx/gun_actions/worm_rain.png"`: Specifies the visual icon for this card in the UI.
    *   **`ItemActionComponent`**:
        *   `_tags="enabled_in_world"`: Makes the action available when the item is in the game world.
        *   `action_id="WORM_RAIN"`: Assigns a unique identifier to this action.

### Visual and Effect Components

*   **`InheritTransformComponent`**:
    *   `_tags="enabled_in_world,enabled_in_hand"`: Ensures this component is active when the item is in the world or held.
    *   **`Transform`**:
        *   `position.x="8"`: Sets the relative X-position of the effect.
        *   `position.y="0"`: Sets the relative Y-position of the effect.

*   **`ParticleEmitterComponent`**: Controls the visual particle effects associated with the card.
    *   `_tags="enabled_in_hand,item_identified"`: Activates particles when the item is held and identified.
    *   `emitted_material_name="plasma_fading_pink"`: The material used for the emitted particles.
    *   `offset.x="0"`, `offset.y="0"`: The center point for particle emission.
    *   `x_pos_offset_min="-4"`, `x_pos_offset_max="4"`: Random horizontal spread of particle origin.
    *   `y_pos_offset_min="-4"`, `y_pos_offset_max="4"`: Random vertical spread of particle origin.
    *   `x_vel_min="-8"`, `x_vel_max="8"`: Minimum and maximum horizontal velocity of particles.
    *   `gravity.y="0.0"`: Particles are not affected by gravity.
    *   `y_vel_min="-8"`, `y_vel_max="8"`: Minimum and maximum vertical velocity of particles.
    *   `count_min="1"`, `count_max="2"`: Number of particles emitted per burst.
    *   `lifetime_min="0.1"`, `lifetime_max="0.6"`: Duration particles exist.
    *   `create_real_particles="0"`: Particles are cosmetic, not physical entities.
    *   `emit_cosmetic_particles="1"`: Enables cosmetic particle emission.
    *   `emission_interval_min_frames="3"`, `emission_interval_max_frames="5"`: Delay between particle bursts.
    *   `is_emitting="1"`: The emitter is active.

*   **`LightComponent`**: Adds a light source when the card is active.
    *   `_tags="enabled_in_hand,item_identified"`: Light is active when the item is held and identified.
    *   `_enabled="1"`: The light component is initially enabled.
    *   `radius="30"`: The radius of the light.
    *   `fade_out_time="1.5"`: How long the light takes to fade out.
    *   `r="80"`, `g="10"`, `b="80"`: The RGB color of the light (a purplish hue).