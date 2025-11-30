---
title: Nuke Giga Custom Card
category: entities
---

# Nuke Giga Custom Card

This document describes the `nuke_giga.xml` entity, which represents a custom spell card in Noita. This card, when activated, triggers a powerful explosive effect.

## Entity Structure

The `nuke_giga.xml` entity is built upon several base components and includes specific configurations for its visual representation, action, and effects.

### Base Components

*   **`data/entities/base_custom_card.xml`**: Provides the fundamental structure for a custom spell card.
    *   **`SpriteComponent`**: Defines the visual appearance of the card in the game's UI.
        *   `image_file`: `data/ui_gfx/gun_actions/nuke_giga.png` - Specifies the texture used for the card's icon.
    *   **`ItemActionComponent`**: Assigns an action ID to the card, enabling its functionality.
        *   `action_id`: `NUKE_GIGA` - The unique identifier for this card's action.

*   **`data/entities/misc/custom_cards/base_high_explosive.xml`**: Inherits properties related to high explosive effects, likely defining the core damage and explosion mechanics.

### Specific Components

*   **`InheritTransformComponent`**: Manages the card's position and orientation when held by the player.
    *   `parent_hotspot_tag`: `shoot_pos` - Indicates that the card's transform should align with the player's shooting position.

*   **`ParticleEmitterComponent`**: Creates visual particle effects when the card is held and identified.
    *   `emitted_material_name`: `spark` - The type of material used for the emitted particles.
    *   `offset.x`, `offset.y`: Controls the initial position of the particles relative to the card.
    *   `x_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_min`, `y_pos_offset_max`: Defines the spread of particle emission.
    *   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Sets the initial velocity range for the particles.
    *   `count_min`, `count_max`: The number of particles emitted per burst.
    *   `lifetime_min`, `lifetime_max`: The duration each particle exists.
    *   `create_real_particles`: `0` - Indicates that these are cosmetic particles, not physical entities.
    *   `emit_cosmetic_particles`: `1` - Enables the emission of cosmetic particles.
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: The delay between particle emission bursts.
    *   `is_emitting`: `1` - Ensures particles are continuously emitted when conditions are met.

*   **`LightComponent`**: Adds a light source to the card when held and identified, illuminating the surroundings.
    *   `radius`: `30` - The range of the light.
    *   `fade_out_time`: `1.5` - How long the light takes to fade.
    *   `r`, `g`, `b`: `120`, `70`, `5` - The RGB color values of the light, giving it a warm, orange hue.