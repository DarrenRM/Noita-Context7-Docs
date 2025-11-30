---
title: Infinite Lifetime Custom Card
category: entities
---

# Infinite Lifetime Custom Card

This entity defines a custom card in Noita that grants the player an "Infinite Lifetime" effect. When held, it visually emits blue sparks and is intended to be used as a modding component.

## Key Components

### Base Entity (`<Base>`)
This entity inherits from `data/entities/base_custom_card.xml`, providing the fundamental structure for a custom card.

*   **SpriteComponent**:
    *   `image_file`: `data/ui_gfx/gun_actions/lifetime_infinite.png` - Specifies the visual representation of the card in the UI.
*   **ItemActionComponent**:
    *   `action_id`: `LIFETIME_INFINITE` - A unique identifier for the action this card performs.
    *   `_tags`: `enabled_in_world` - Indicates the card is active when in the game world.

### Transform Component (`<InheritTransformComponent>`)
This component manages the positioning and orientation of the card when held by the player.

*   `_tags`: `enabled_in_world,enabled_in_hand` - The component is active when the card is in the world and specifically when held.
*   `parent_hotspot_tag`: `shoot_pos` - Aligns the card's transform relative to the player's shooting position.

### Particle Emitter Component (`<ParticleEmitterComponent>`)
This component is responsible for generating visual effects when the card is held.

*   `_tags`: `enabled_in_hand,item_identified` - The emitter is active when the item is held and identified.
*   `emitted_material_name`: `spark_blue` - The type of particle to emit.
*   `offset.x`, `offset.y`: `0` - The center of the emission relative to the parent.
*   `x_pos_offset_min`, `x_pos_offset_max`: `-3` to `3` - The horizontal spread of emitted particles.
*   `y_pos_offset_min`, `y_pos_offset_max`: `1` to `-1` - The vertical spread of emitted particles.
*   `x_vel_min`, `x_vel_max`: `-2` to `2` - The horizontal velocity range of emitted particles.
*   `y_vel_min`, `y_vel_max`: `-20` to `-10` - The vertical velocity range of emitted particles (upwards).
*   `count_min`, `count_max`: `1` to `2` - The number of particles emitted per burst.
*   `lifetime_min`, `lifetime_max`: `0.2` to `0.3` - The duration each particle exists.
*   `create_real_particles`: `0` - Particles are cosmetic and do not interact physically.
*   `emit_cosmetic_particles`: `1` - Enables the emission of cosmetic particles.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: `8` to `14` - The frame interval between particle emission bursts.
*   `is_emitting`: `1` - The particle emitter is active.