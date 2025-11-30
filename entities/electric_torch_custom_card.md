---
title: Electric Torch Custom Card
category: entities
---

# Electric Torch Custom Card

This document details the configuration for the "Electric Torch" custom card entity in Noita, focusing on its visual, functional, and interactive components.

## Base Entity Configuration

The core of the Electric Torch is built upon a `base_custom_card.xml`.

### Key Components:

*   **`SpriteComponent`**: Defines the visual representation of the card in the UI.
    *   `image_file`: `data/ui_gfx/gun_actions/torch_electric.png` - Specifies the texture for the card's icon.
*   **`ItemActionComponent`**: Assigns an action ID to the card, enabling its functionality.
    *   `action_id`: `TORCH_ELECTRIC` - The unique identifier for this card's action.
    *   `_tags`: `enabled_in_world` - Indicates the card is active when in the game world.

## In-Hand Visuals and Effects

These components define how the Electric Torch appears and behaves when held by the player.

### Key Components:

*   **`InheritTransformComponent`**: Positions the visual elements relative to the player's hand.
    *   `Transform`: `position.x="8"`, `position.y="0"` - Offsets the item's origin.
*   **`ParticleEmitterComponent` (Plasma Fading)**: Creates cosmetic particles for a visual effect.
    *   `emitted_material_name`: `plasma_fading`
    *   `offset.x`, `offset.y`: Centered on the item.
    *   `x_pos_offset_min/max`, `y_pos_offset_min/max`: Defines the spread area for particles.
    *   `x_vel_min/max`, `y_vel_min/max`: Controls particle velocity and direction.
    *   `count_min/max`: Number of particles emitted per burst.
    *   `lifetime_min/max`: Duration each particle exists.
    *   `create_real_particles`: `0` (cosmetic only).
    *   `emit_cosmetic_particles`: `1` (enables cosmetic particle emission).
    *   `emission_interval_min_frames/max_frames`: Controls the rate of emission.
    *   `is_emitting`: `1` (particle emission is active).
*   **`LightComponent` (Primary)**: Provides a larger ambient light source.
    *   `radius`: `130` - The range of the light.
    *   `fade_out_time`: `1.5` - How long the light fades.
    *   `r`, `g`, `b`: `220`, `180`, `240` - A purplish-white color.
*   **`LightComponent` (Secondary)**: Provides a smaller, brighter light source.
    *   `radius`: `32`
    *   `fade_out_time`: `1.5`
    *   `r`, `g`, `b`: `255`, `255`, `255` - White light.
*   **`ParticleEmitterComponent` (Steam)**: Emits real particles for a more tangible effect.
    *   `emitted_material_name`: `steam`
    *   `offset.x/y`: Centered.
    *   `y_pos_offset_min/max`: Slight vertical offset.
    *   `x_vel_min/max`, `y_vel_min/max`: No significant velocity.
    *   `count_min/max`: `5` particles.
    *   `lifetime_min/max`: Short lifespan.
    *   `create_real_particles`: `1` (actual game particles).
    *   `emit_cosmetic_particles`: `0`.
    *   `emission_interval_min_frames/max_frames`: Controls the rate of steam emission.
*   **`SpriteComponent` (Fog of War Hole)**: Creates a visual hole in the fog of war.
    *   `image_file`: `data/particles/torch_electric_fog_of_war_hole.xml`
    *   `fog_of_war_hole`: `1` - Enables the fog of war effect.
    *   `special_scale_x/y`: `4` - Scales the fog of war hole effect.
*   **`AudioComponent`**: Plays the initial sound effect when the torch is activated.
    *   `file`: `data/audio/Desktop/projectiles.bank`
    *   `event_root`: `player_projectiles/torch_electric`
*   **`AudioLoopComponent`**: Plays a continuous looping sound effect while the torch is active.
    *   `file`: `data/audio/Desktop/projectiles.bank`
    *   `event_name`: `player_projectiles/torch_electric/loop`
    *   `auto_play_if_enabled`: `1`
    *   `play_on_component_enable`: `1`
*   **`SpriteParticleEmitterComponent` (Sparks)**: Emits small spark particles.
    *   `sprite_file`: `data/particles/spark_electric.xml`
    *   `emission_interval_min_frames/max_frames`: Controls spark emission rate.
    *   `count_min/max`: `1` spark per emission.
    *   `randomize_rotation.min/max`: Randomizes spark orientation.
    *   `randomize_position.min/max_x/y`: Spreads sparks around the torch.
    *   `randomize_velocity.min/max_x/y`: Adds slight random movement to sparks.
*   **`ParticleEmitterComponent` (Blue Sparks)**: Emits cosmetic blue sparks.
    *   `emitted_material_name`: `spark_blue`
    *   `x_pos_offset_min/max`, `y_pos_offset_min/max`: Defines the spark emission area.
    *   `x_vel_min/max`, `y_vel_min/max`: Controls spark velocity.
    *   `count_min/max`: `1` spark per emission.
    *   `gravity.y`: `0` (no gravity effect on these sparks).
    *   `lifetime_min/max`: Short lifespan for sparks.
    *   `create_real_particles`: `0` (cosmetic).
    *   `emit_cosmetic_particles`: `1`.
    *   `emission_interval_min_frames/max_frames`: Controls spark emission rate.
    *   `is_emitting`: `1`.

## Functionality

### Key Components:

*   **`ElectricitySourceComponent`**: Enables the entity to act as a source of electricity.
    *   `radius`: `4` - The range at which electricity can be emitted or detected.
    *   `emission_interval_frames`: `32` - The frequency of electrical pulses.