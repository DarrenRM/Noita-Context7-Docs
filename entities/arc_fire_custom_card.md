---
title: Arc Fire Custom Card
category: entities
---

# Arc Fire Custom Card

This document describes the "Arc Fire" custom card entity in Noita, focusing on its key attributes for AI-assisted modding.

## Entity Definition

The `arc_fire.xml` file defines a custom card entity that, when held, emits particles and a light effect.

### Base Components

*   **`Base file="data/entities/base_custom_card.xml"`**: Inherits core functionality from the base custom card.
    *   **`SpriteComponent`**: Defines the visual representation of the card in the UI.
        *   `image_file="data/ui_gfx/gun_actions/arc_fire.png"`: Specifies the sprite image for the card.
    *   **`ItemActionComponent`**: Assigns an action ID to the card.
        *   `action_id="ARC_FIRE"`: Identifies the specific action this card performs.

### Transform and Visuals

*   **`InheritTransformComponent`**: Controls the positioning of the card when held.
    *   `position.x="8"`: Horizontal offset.
    *   `position.y="0"`: Vertical offset.

### Particle Emitters

The card utilizes multiple `ParticleEmitterComponent` instances to create visual effects.

*   **Particle Emitter 1 (Cosmetic Sparks)**
    *   `_tags="enabled_in_hand,item_identified"`: Active when the item is held and identified.
    *   `emitted_material_name="spark"`: The type of particle emitted.
    *   `count_min="1"`, `count_max="2"`: Number of particles per emission.
    *   `lifetime_min="0.4"`, `lifetime_max="0.6"`: Duration of each particle.
    *   `create_real_particles="0"`: These are purely cosmetic.
    *   `emission_interval_min_frames="5"`, `emission_interval_max_frames="15"`: Frequency of particle emission.

*   **Particle Emitter 2 (Real Sparks)**
    *   `_tags="enabled_in_hand,item_identified"`: Active when the item is held and identified.
    *   `emitted_material_name="spark"`: The type of particle emitted.
    *   `count_min="1"`, `count_max="1"`: Number of particles per emission.
    *   `lifetime_min="0.4"`, `lifetime_max="0.6"`: Duration of each particle.
    *   `create_real_particles="1"`: These are actual game particles.
    *   `emission_interval_min_frames="15"`, `emission_interval_max_frames="25"`: Frequency of particle emission.

*   **Particle Emitter 3 (Smoke)**
    *   `_tags="enabled_in_hand,item_identified"`: Active when the item is held and identified.
    *   `emitted_material_name="smoke"`: The type of particle emitted.
    *   `count_min="1"`, `count_max="1"`: Number of particles per emission.
    *   `lifetime_min="0.4"`, `lifetime_max="0.6"`: Duration of each particle.
    *   `create_real_particles="1"`: These are actual game particles.
    *   `emission_interval_min_frames="15"`, `emission_interval_max_frames="30"`: Frequency of particle emission.

### Light Component

*   **`LightComponent`**: Adds a light source when the card is active.
    *   `_tags="enabled_in_hand,item_identified"`: Active when the item is held and identified.
    *   `radius="30"`: The radius of the light.
    *   `fade_out_time="1.5"`: How long the light takes to fade.
    *   `r="120"`, `g="80"`, `b="10"`: RGB color values for the light (warm orange/yellow).