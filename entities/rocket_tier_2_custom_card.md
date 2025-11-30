---
title: Rocket Tier 2 Custom Card
category: entities
---

# Rocket Tier 2 Custom Card

This document details the configuration for the "Rocket Tier 2" custom card entity in Noita, intended for AI-assisted modding.

## Core Entity Configuration

The `Entity` tag encloses all components defining the custom card.

### Base Component

The `Base` component inherits from `data/entities/base_custom_card.xml`, providing fundamental properties for custom cards.

*   **`SpriteComponent`**:
    *   `image_file`: `data/ui_gfx/gun_actions/rocket_tier_2.png` - Specifies the visual representation of the card in the UI.

*   **`ItemActionComponent`**:
    *   `_tags`: `enabled_in_world` - Indicates the action is available when the item is in the game world.
    *   `action_id`: `ROCKET_TIER_2` - A unique identifier for this specific action.

### Transform Component

*   **`InheritTransformComponent`**:
    *   `_tags`: `enabled_in_world,enabled_in_hand` - The transform is active when the item is in the world or held by the player.
    *   `parent_hotspot_tag`: `shoot_pos` - The transform is inherited from the entity's `shoot_pos` hotspot, typically used for aiming and firing.

### Visual Effects

*   **`ParticleEmitterComponent`**: This component generates cosmetic particles when the item is identified and held.
    *   `_tags`: `enabled_in_hand,item_identified` - Particles are emitted when the item is held and its properties are known.
    *   `emitted_material_name`: `spark_green` - The type of particle material to emit.
    *   `offset.x`, `offset.y`: `0` - The center of the emission.
    *   `x_pos_offset_min`, `x_pos_offset_max`: `-2` to `2` - Horizontal spread of particle emission.
    *   `y_pos_offset_min`, `y_pos_offset_max`: `2` to `-2` - Vertical spread of particle emission.
    *   `x_vel_min`, `x_vel_max`: `-2` to `2` - Horizontal velocity range for emitted particles.
    *   `y_vel_min`, `y_vel_max`: `-20` to `-10` - Vertical velocity range for emitted particles (upward direction).
    *   `count_min`, `count_max`: `1` to `2` - Number of particles emitted per burst.
    *   `lifetime_min`, `lifetime_max`: `0.2` to `0.3` - Duration of each particle in seconds.
    *   `create_real_particles`: `0` - Particles are cosmetic and do not interact physically.
    *   `emit_cosmetic_particles`: `1` - Enables the emission of cosmetic particles.
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: `8` to `15` - The frame interval between particle emission bursts.
    *   `is_emitting`: `1` - The particle emitter is active by default.

*   **`LightComponent`**: Adds a light source when the item is identified and held.
    *   `_tags`: `enabled_in_hand,item_identified` - The light is active when the item is held and identified.
    *   `_enabled`: `1` - The light component is enabled by default.
    *   `radius`: `30` - The radius of the light.
    *   `fade_out_time`: `1.5` - The time it takes for the light to fade out.
    *   `r`, `g`, `b`: `70`, `120`, `5` - The RGB color values of the light (a greenish-yellow hue).