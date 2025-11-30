---
title: Custom Card - Grenade Tier 2
category: entities
---

# Custom Card - Grenade Tier 2

This document details the configuration for the "Grenade Tier 2" custom card entity in Noita, intended for AI-assisted modding.

## Core Entity Configuration

The `Grenade_tier_2.xml` file defines a custom card entity that functions as a grenade. It inherits from `base_custom_card.xml` and includes specific components for its visual representation, action, and particle effects.

### Key Components and Attributes

*   **`<Base>`**:
    *   `file="data/entities/base_custom_card.xml"`: Inherits fundamental properties of a custom card.
    *   **`<SpriteComponent>`**:
        *   `image_file="data/ui_gfx/gun_actions/grenade_tier_2.png"`: Specifies the UI icon for this card.
    *   **`<ItemActionComponent>`**:
        *   `_tags="enabled_in_world"`: Makes the action available in the game world.
        *   `action_id="GRENADE_TIER_2"`: The unique identifier for this grenade action.

*   **`<InheritTransformComponent>`**:
    *   `_tags="enabled_in_world,enabled_in_hand"`: Ensures the transform is applied when the item is in the world or in hand.
    *   `parent_hotspot_tag="shoot_pos"`: Defines the origin point for shooting or throwing.

*   **`<ParticleEmitterComponent>`**:
    *   `_tags="enabled_in_hand,item_identified"`: Activates particle emission when the item is held and identified.
    *   `emitted_material_name="spark_green"`: The type of particle to emit.
    *   `offset.x`, `offset.y`: Controls the particle emission origin relative to the parent.
    *   `x_pos_offset_min/max`, `y_pos_offset_min/max`: Defines the spread area for emitted particles.
    *   `x_vel_min/max`, `y_vel_min/max`: Sets the initial velocity range for particles.
    *   `count_min/max`: The number of particles emitted per burst.
    *   `lifetime_min/max`: Duration each particle exists.
    *   `create_real_particles="0"`: Indicates these are cosmetic particles, not physical entities.
    *   `emit_cosmetic_particles="1"`: Confirms cosmetic particle emission.
    *   `emission_interval_min_frames/max_frames`: Controls the timing between particle bursts.
    *   `is_emitting="1"`: Enables continuous emission while conditions are met.

*   **`<LightComponent>`**:
    *   `_tags="enabled_in_hand,item_identified"`: Activates the light when the item is held and identified.
    *   `_enabled="1"`: Ensures the light component is active.
    *   `radius="30"`: The range of the light.
    *   `fade_out_time="1.5"`: How long the light takes to fade.
    *   `r="70"`, `g="120"`, `b="5"`: Defines the RGB color of the light (a greenish hue).