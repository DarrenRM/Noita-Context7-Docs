---
title: Heal Bullet Custom Card
category: entities
---

# Heal Bullet Custom Card

This document describes the `heal_bullet.xml` entity, which defines a custom card in Noita that heals the player when used.

## Key Components

This entity inherits from `base_custom_card.xml` and adds several components to define its behavior and appearance.

### Base Custom Card

*   **`SpriteComponent`**: Defines the visual representation of the card in the UI.
    *   `image_file`: `data/ui_gfx/gun_actions/heal_bullet.png` - Specifies the sprite used for the card.
*   **`ItemActionComponent`**: Assigns an action ID to the card.
    *   `action_id`: `HEAL_BULLET` - Identifies the specific action this card performs.

### Inherit Transform Component

*   **`InheritTransformComponent`**: Controls the positioning of the card when held.
    *   `Transform`:
        *   `position.x`: `8`
        *   `position.y`: `0` - Offsets the card slightly when held.

### Sprite Particle Emitter Component

*   **`SpriteParticleEmitterComponent`**: Manages the emission of sprite-based particles when the card is in hand and identified.
    *   `sprite_file`: `data/particles/heal.xml` - Links to the particle definition for healing effects.
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the timing of particle emissions.
    *   `count_min`, `count_max`: Determines the number of particles emitted per interval.
    *   `randomize_rotation`, `randomize_angular_velocity`, `randomize_position`, `randomize_velocity`: Adds variation to emitted particles for a more dynamic effect.
    *   `is_emitting`: `0` - This tag seems to indicate it's not actively emitting by default, likely controlled by other tags like `item_identified`.

### Particle Emitter Component

*   **`ParticleEmitterComponent`**: Manages the emission of material-based particles.
    *   `emitted_material_name`: `spark_green` - The material used for these particles.
    *   `lifetime_min`, `lifetime_max`: Duration of emitted particles.
    *   `count_min`, `count_max`: Number of particles emitted.
    *   `area_circle_radius.max`: Defines the area from which particles can be emitted.
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the timing of particle emissions.
    *   `is_emitting`: `1` - Actively emits particles when conditions are met.

### Light Component

*   **`LightComponent`**: Adds a light source when the card is held and identified.
    *   `radius`: `30` - The range of the light.
    *   `fade_out_time`: `1.5` - How long the light fades out.
    *   `r`, `g`, `b`: `80`, `10`, `80` - Defines the color of the light (a purplish hue).