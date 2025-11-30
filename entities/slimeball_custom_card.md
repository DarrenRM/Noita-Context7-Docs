---
title: Slimeball Custom Card
category: entities
---

# Slimeball Custom Card

This document details the configuration for the "Slimeball" custom card entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core of the Slimeball card is defined by an `<Entity>` tag.

### Base Configuration

The card inherits its fundamental properties from `base_custom_card.xml`.

*   **`SpriteComponent`**:
    *   `image_file`: `data/ui_gfx/gun_actions/slimeball.png` - Specifies the visual representation of the card in the UI.

*   **`ItemActionComponent`**:
    *   `_tags`: `enabled_in_world,enabled_in_hand` - Makes the card functional when in the game world or held by the player.
    *   `action_id`: `SLIMEBALL` - A unique identifier for this action.

### Transform Component

*   **`InheritTransformComponent`**:
    *   `_tags`: `enabled_in_world,enabled_in_hand` - Ensures the transform is applied when the card is active.
    *   **`Transform`**:
        *   `position.x`: `5`
        *   `position.y`: `0` - Defines the relative position of the card's visual elements when held.

### Particle Emitters

The Slimeball card utilizes two `ParticleEmitterComponent` instances to create visual effects when held.

1.  **Acid Gas Effect**:
    *   `_tags`: `enabled_in_hand,item_identified` - Active when the item is held and identified.
    *   `emitted_material_name`: `acid_gas` - The material that forms the particles.
    *   `offset.x`, `offset.y`: `0, 0` - Centered on the item.
    *   **Position Offsets**:
        *   `x_pos_offset_min`: `-5`, `x_pos_offset_max`: `5`
        *   `y_pos_offset_min`: `2`, `y_pos_offset_max`: `-2` - Particles spread around the item.
    *   **Velocity**:
        *   `x_vel_min`: `-2`, `x_vel_max`: `2`
        *   `y_vel_min`: `-20`, `y_vel_max`: `-10` - Particles are primarily ejected upwards.
    *   **Count**: `count_min="1"`, `count_max="1"` - Emits one particle at a time.
    *   **Lifetime**: `lifetime_min="0.2"`, `lifetime_max="0.3"` - Short lifespan.
    *   `create_real_particles`: `1` - Creates actual game particles.
    *   `emit_cosmetic_particles`: `1` - Also emits visual-only particles.
    *   **Emission Interval**: `emission_interval_min_frames="10"`, `emission_interval_max_frames="25"` - Controls the rate of emission.
    *   `is_emitting`: `1` - The emitter is active.

2.  **Radioactive Liquid Fading Effect**:
    *   `_tags`: `enabled_in_hand,item_identified` - Active when the item is held and identified.
    *   `emitted_material_name`: `radioactive_liquid_fading` - The material for these particles.
    *   `offset.x`, `offset.y`: `0, 0` - Centered on the item.
    *   **Position Offsets**:
        *   `x_pos_offset_min`: `-1`, `x_pos_offset_max`: `1`
        *   `y_pos_offset_min`: `-1`, `y_pos_offset_max`: `1` - Particles are tightly clustered around the item.
    *   **Velocity**:
        *   `x_vel_min`: `-10`, `x_vel_max`: `10`
        *   `y_vel_min`: `-10`, `y_vel_max`: `10` - Particles have a more varied velocity.
    *   **Count**: `count_min="5"`, `count_max="5"` - Emits 5 particles per burst.
    *   **Lifetime**: `lifetime_min="0.1"`, `lifetime_max="0.6"` - Short to moderate lifespan.
    *   `create_real_particles`: `0` - Only emits cosmetic particles.
    *   `emit_cosmetic_particles`: `1` - Emits visual-only particles.
    *   **Emission Interval**: `emission_interval_min_frames="15"`, `emission_interval_max_frames="25"` - Controls the rate of emission.
    *   `is_emitting`: `1` - The emitter is active.