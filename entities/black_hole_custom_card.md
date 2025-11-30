---
title: Black Hole Custom Card
category: entities
---

# Black Hole Custom Card

This document describes the configuration for the "Black Hole" custom card entity in Noita, intended for AI-assisted modding.

## Entity Definition

The `Black Hole` entity is defined as a custom card, inheriting from `base_custom_card.xml`.

### Key Components

*   **Base Component**:
    *   `file`: `data/entities/base_custom_card.xml` - Specifies the base entity type.
    *   `SpriteComponent`:
        *   `image_file`: `data/ui_gfx/gun_actions/black_hole.png` - The visual representation of the card in the UI.
    *   `ItemActionComponent`:
        *   `action_id`: `BLACK_HOLE` - Unique identifier for the action this card performs.
        *   `_tags`: `enabled_in_world` - Indicates the action is available when the item is in the game world.

*   **InheritTransformComponent**:
    *   `_tags`: `enabled_in_world,enabled_in_hand` - Applies when the item is in the world or held by the player.
    *   `Transform`:
        *   `position.x`: `8` - X-axis offset for the item's transform.
        *   `position.y`: `0` - Y-axis offset for the item's transform.

*   **ParticleEmitterComponent**:
    *   `_tags`: `enabled_in_hand,item_identified` - Active when the item is held and identified.
    *   `emitted_material_name`: `plasma_fading_pink` - The material used for emitted particles.
    *   `offset.x`, `offset.y`: `0` - Center of particle emission.
    *   `x_pos_offset_min`, `x_pos_offset_max`: `-4` to `4` - Horizontal spread of particle emission.
    *   `y_pos_offset_min`, `y_pos_offset_max`: `-4` to `4` - Vertical spread of particle emission.
    *   `x_vel_min`, `x_vel_max`: `-8` to `8` - Minimum and maximum horizontal velocity of particles.
    *   `y_vel_min`, `y_vel_max`: `-8` to `8` - Minimum and maximum vertical velocity of particles.
    *   `gravity.y`: `0.0` - No vertical gravity applied to particles.
    *   `count_min`, `count_max`: `1` to `2` - Number of particles emitted per burst.
    *   `lifetime_min`, `lifetime_max`: `0.1` to `0.6` - Duration particles exist.
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: `5` to `15` - Frame interval between particle emissions.
    *   `create_real_particles`: `0` - Particles are cosmetic, not physical entities.
    *   `emit_cosmetic_particles`: `1` - Enables cosmetic particle emission.
    *   `is_emitting`: `1` - The emitter is active.

*   **LightComponent**:
    *   `_tags`: `enabled_in_hand,item_identified` - Active when the item is held and identified.
    *   `_enabled`: `1` - The light component is active.
    *   `radius`: `30` - The radius of the light effect.
    *   `fade_out_time`: `1.5` - Time it takes for the light to fade out.
    *   `r`, `g`, `b`: `80`, `10`, `80` - RGB color values for the light (a purplish hue).