---
title: Midas Custom Card
category: entities
---

# Midas Custom Card

This document details the `midas.xml` entity, representing a custom card in Noita that imbues the player with the power of gold.

## Core Components

### Base Entity (`Base file="data/entities/base_custom_card.xml"`)

This entity inherits from a base custom card, providing fundamental properties for cards.

*   **SpriteComponent**: Defines the visual representation of the card.
    *   `image_file`: `data/ui_gfx/gun_actions/midas.png` - Specifies the texture used for the card's icon.
*   **ItemActionComponent**: Assigns an action ID to the card.
    *   `action_id`: `MIDAS` - This ID is crucial for game logic to recognize and trigger the card's effects.
    *   `_tags`: `enabled_in_world` - Indicates the card is active when in the game world.

### Transform (`InheritTransformComponent`)

This component handles the positioning and orientation of the card when held.

*   `_tags`: `enabled_in_world,enabled_in_hand` - The card is active both in the world and when held by the player.
*   **Transform**: Defines the relative position.
    *   `position.x`: `8`
    *   `position.y`: `0`

## Particle Effects

The Midas card utilizes two `ParticleEmitterComponent`s to create visual feedback when identified.

### Gold Particle Emitter

This emitter generates actual gold particles.

*   `_tags`: `enabled_in_hand,item_identified` - Active when the card is held and identified.
*   `emitted_material_name`: `gold` - The material to be emitted.
*   `offset.x`, `offset.y`: `0` - Centered emission.
*   **Position Offsets**:
    *   `x_pos_offset_min`: `-3`
    *   `x_pos_offset_max`: `3`
    *   `y_pos_offset_min`: `1`
    *   `y_pos_offset_max`: `-1`
*   **Velocity**:
    *   `x_vel_min`: `-10`
    *   `x_vel_max`: `10`
    *   `y_vel_min`: `-20`
    *   `y_vel_max`: `-10`
*   `count_min`, `count_max`: `1` - Emits a single particle per emission.
*   `lifetime_min`, `lifetime_max`: `0.4` to `0.5` seconds.
*   `create_real_particles`: `1` - Generates actual game entities.
*   `emit_cosmetic_particles`: `0` - Does not emit purely visual particles.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: `30` to `42` frames - Controls the rate of emission.
*   `is_emitting`: `1` - The emitter is active.

### Spark Particle Emitter

This emitter generates cosmetic yellow sparks.

*   `_tags`: `enabled_in_hand,item_identified` - Active when the card is held and identified.
*   `emitted_material_name`: `spark_yellow` - The material to be emitted.
*   `offset.x`, `offset.y`: `0` - Centered emission.
*   `gravity.y`: `10` - Applies gravity to the sparks.
*   **Position Offsets**:
    *   `x_pos_offset_min`: `-3`
    *   `x_pos_offset_max`: `3`
    *   `y_pos_offset_min`: `1`
    *   `y_pos_offset_max`: `-1`
*   **Velocity**:
    *   `x_vel_min`: `-10`
    *   `x_vel_max`: `10`
    *   `y_vel_min`: `-20`
    *   `y_vel_max`: `-10`
*   `count_min`, `count_max`: `1` to `2` particles per emission.
*   `lifetime_min`, `lifetime_max`: `0.4` to `1.5` seconds.
*   `render_on_grid`: `1` - Renders particles on the game grid.
*   `fade_based_on_lifetime`: `1` - Particles fade out as their lifetime ends.
*   `create_real_particles`: `0` - Does not generate actual game entities.
*   `emit_cosmetic_particles`: `1` - Emits purely visual particles.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: `3` to `12` frames - Controls the rate of emission.
*   `is_emitting`: `1` - The emitter is active.