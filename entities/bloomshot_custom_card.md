---
title: Bloomshot Custom Card
category: entities
---

# Bloomshot Custom Card

This document details the `bloomshot.xml` entity, which defines a custom spell card in Noita.

## Core Components

### Base Entity

The `Base` component inherits from `base_custom_card.xml`, providing fundamental properties for custom spell cards.

*   **`SpriteComponent`**: Defines the visual representation of the card in the UI.
    *   `image_file`: `data/ui_gfx/gun_actions/bloomshot.png` - Specifies the texture for the card's icon.
*   **`ItemActionComponent`**: Assigns an action ID to the card, linking it to game mechanics.
    *   `action_id`: `BLOOMSHOT` - The unique identifier for this spell's action.
    *   `_tags`: `enabled_in_world` - Indicates the card is active when in the game world.

### Transform Component

*   **`InheritTransformComponent`**: Manages the positioning of the card when held.
    *   `_tags`: `enabled_in_world,enabled_in_hand` - The component is active when the card is in the world and held by the player.
    *   **`Transform`**: Defines the relative position.
        *   `position.x`: `5`
        *   `position.y`: `0`

## Particle Emitters

These components define visual effects associated with the card when it's held and identified.

### Emitter 1: Acid Gas

*   **`ParticleEmitterComponent`**: Creates cosmetic particles to enhance the visual feedback.
    *   `_tags`: `enabled_in_hand,item_identified` - Active when the item is held and its identity is known.
    *   `emitted_material_name`: `acid_gas` - The material used for the emitted particles.
    *   `offset.x`, `offset.y`: `0`, `0` - The center of emission.
    *   **Position Offset**:
        *   `x_pos_offset_min`: `-5`
        *   `x_pos_offset_max`: `5`
        *   `y_pos_offset_min`: `2`
        *   `y_pos_offset_max`: `-2`
    *   **Velocity**:
        *   `x_vel_min`: `-2`
        *   `x_vel_max`: `2`
        *   `y_vel_min`: `-20`
        *   `y_vel_max`: `-10`
    *   **Count**:
        *   `count_min`: `1`
        *   `count_max`: `1`
    *   **Lifetime**:
        *   `lifetime_min`: `0.2`
        *   `lifetime_max`: `0.3`
    *   `create_real_particles`: `1` - Creates actual game particles.
    *   `emit_cosmetic_particles`: `1` - Emits cosmetic particles.
    *   **Emission Interval**:
        *   `emission_interval_min_frames`: `10`
        *   `emission_interval_max_frames`: `25`
    *   `is_emitting`: `1` - The emitter is active.

### Emitter 2: Radioactive Liquid Fading

*   **`ParticleEmitterComponent`**: Another emitter for distinct visual effects.
    *   `_tags`: `enabled_in_hand,item_identified`
    *   `emitted_material_name`: `radioactive_liquid_fading`
    *   `offset.x`, `offset.y`: `0`, `0`
    *   **Position Offset**:
        *   `x_pos_offset_min`: `-1`
        *   `y_pos_offset_min`: `-1`
        *   `x_pos_offset_max`: `1`
        *   `y_pos_offset_max`: `1`
    *   **Velocity**:
        *   `x_vel_min`: `-10`
        *   `x_vel_max`: `10`
        *   `y_vel_min`: `-10`
        *   `y_vel_max`: `10`
    *   **Count**:
        *   `count_min`: `5`
        *   `count_max`: `5`
    *   **Lifetime**:
        *   `lifetime_min`: `0.1`
        *   `lifetime_max`: `0.6`
    *   `create_real_particles`: `0` - Does not create real game particles.
    *   `emit_cosmetic_particles`: `1` - Emits cosmetic particles.
    *   **Emission Interval**:
        *   `emission_interval_min_frames`: `15`
        *   `emission_interval_max_frames`: `25`
    *   `is_emitting`: `1` - The emitter is active.