---
title: Acid Trail Custom Card
category: entities
---

# Acid Trail Custom Card

This document details the `acid_trail.xml` entity, which defines a custom card in Noita that creates an acid trail effect.

## Entity Definition

The core of this entity is a custom card that, when used, emits particles of `acid_gas`.

### Base Components

*   **`Base file="data/entities/base_custom_card.xml"`**: Inherits fundamental properties of a custom card.
    *   **`SpriteComponent`**: Defines the visual representation of the card in the UI.
        *   `image_file="data/ui_gfx/gun_actions/acid_trail.png"`: Specifies the icon used for this card.
    *   **`ItemActionComponent`**: Assigns an action ID to this card.
        *   `action_id="ACID_TRAIL"`: Identifies the specific action this card performs.

### Transform Component

*   **`InheritTransformComponent`**: Controls the positioning of the effect relative to the player's hand.
    *   **`Transform`**:
        *   `position.x="5"`: Offsets the effect 5 units to the right.
        *   `position.y="0"`: No vertical offset.

### Particle Emitter Component

*   **`ParticleEmitterComponent`**: Manages the emission of particles to create the acid trail.
    *   `emitted_material_name="acid_gas"`: The material that will be emitted as particles.
    *   `x_pos_offset_min="-5"`, `x_pos_offset_max="5"`: Random horizontal spread for particle emission.
    *   `y_pos_offset_min="2"`, `y_pos_offset_max="-2"`: Random vertical spread for particle emission.
    *   `x_vel_min="-2"`, `x_vel_max="2"`: Controls the horizontal velocity of emitted particles.
    *   `y_vel_min="-20"`, `y_vel_max="-10"`: Controls the downward vertical velocity of emitted particles, creating a falling effect.
    *   `count_min="1"`, `count_max="1"`: Emits one particle per emission cycle.
    *   `lifetime_min="0.2"`, `lifetime_max="0.3"`: Duration each particle exists.
    *   `create_real_particles="1"`: Enables the creation of actual game particles.
    *   `emit_cosmetic_particles="1"`: Enables the creation of cosmetic particles (visual only).
    *   `emission_interval_min_frames="10"`, `emission_interval_max_frames="25"`: The delay between particle emission bursts.
    *   `is_emitting="1"`: Ensures the particle emitter is active.