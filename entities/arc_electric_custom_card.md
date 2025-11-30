---
title: Arc Electric Custom Card
category: entities
---

# Arc Electric Custom Card

This document details the configuration for the "Arc Electric" custom card entity in Noita, intended for AI-assisted modding.

## Entity Definition

The core of this entity is based on `base_custom_card.xml`, providing fundamental properties for a custom card item.

### Key Components

*   **`Base`**: Inherits from `data/entities/base_custom_card.xml`.
    *   **`SpriteComponent`**: Defines the visual representation of the card in the UI.
        *   `image_file`: `data/ui_gfx/gun_actions/arc_electric.png`
    *   **`ItemActionComponent`**: Assigns an action ID to the card.
        *   `action_id`: `ARC_ELECTRIC`
        *   `_tags`: `enabled_in_world` (Indicates the card is active in the game world).

*   **`InheritTransformComponent`**: Manages the card's position relative to the player's hand.
    *   `_tags`: `enabled_in_world`, `enabled_in_hand`
    *   **`Transform`**: Specifies the offset from the hand.
        *   `position.x`: `8`
        *   `position.y`: `0`

*   **`SpriteParticleEmitterComponent`**: Controls the visual particle effects when the card is held and identified.
    *   `_tags`: `enabled_in_hand`, `item_identified`
    *   `sprite_file`: `data/particles/arc.xml` (References the particle definition for the arc effect).
    *   **Key Emission Properties**:
        *   `delay`: `0`
        *   `lifetime`: `0`
        *   `color.r`, `color.g`, `color.b`, `color.a`: `1`, `1`, `1`, `1` (White color).
        *   `gravity.y`: `10`
        *   `emission_interval_min_frames`, `emission_interval_max_frames`: `10`, `25` (Controls particle spawn rate).
        *   `count_min`, `count_max`: `1`, `1` (Spawns a single particle per emission).
        *   `randomize_rotation.min`, `randomize_rotation.max`: `-3.1415`, `3.1415` (Full rotation randomization).
        *   `randomize_position.min_x`, `randomize_position.max_x`: `-4`, `4`
        *   `randomize_position.min_y`, `randomize_position.max_y`: `-2`, `2`
        *   `randomize_velocity.min_x`, `randomize_velocity.max_x`: `-30`, `30`
        *   `randomize_velocity.min_y`, `randomize_velocity.max_y`: `-30`, `30`

*   **`ParticleEmitterComponent`**: Generates cosmetic particles associated with the electric arc.
    *   `_tags`: `enabled_in_hand`, `item_identified`
    *   `emitted_material_name`: `spark_blue` (Specifies the type of particle to emit).
    *   **Key Emission Properties**:
        *   `offset.x`, `offset.y`: `0`, `0`
        *   `x_pos_offset_min`, `x_pos_offset_max`: `-3`, `3`
        *   `y_pos_offset_min`, `y_pos_offset_max`: `-1`, `1`
        *   `x_vel_min`, `x_vel_max`: `-2`, `2`
        *   `y_vel_min`, `y_vel_max`: `-20`, `-10` (Particles are primarily shot upwards).
        *   `count_min`, `count_max`: `1`, `1`
        *   `lifetime_min`, `lifetime_max`: `0.2`, `0.3`
        *   `create_real_particles`: `0` (Only cosmetic particles).
        *   `emit_cosmetic_particles`: `1`
        *   `emission_interval_min_frames`, `emission_interval_max_frames`: `10`, `25`
        *   `is_emitting`: `1`

*   **`LightComponent`**: Adds a light source when the card is active.
    *   `_tags`: `enabled_in_hand`, `item_identified`
    *   `_enabled`: `1`
    *   `radius`: `40`
    *   `fade_out_time`: `1.5`
    *   `r`, `g`, `b`: `20`, `40`, `150` (Blueish light).

*   **`Base`**: Inherits from `data/entities/particles/water_electrocution.xml`. This likely applies the electrocution effect when the card interacts with water.