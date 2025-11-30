---
title: Rocket Custom Card Entity
category: entities
---

# Rocket Custom Card Entity

This document describes the `rocket.xml` entity, which defines a custom card in Noita that functions as a "Rocket". This entity is designed to be used as an item that players can acquire and use.

## Base Entity Configuration

The core of this entity is built upon a base custom card template.

### `Base` Element

*   **`file`**: `data/entities/base_custom_card.xml`
    *   This indicates that the entity inherits its fundamental properties and behaviors from the standard custom card template.

### `SpriteComponent`

*   **`image_file`**: `data/ui_gfx/gun_actions/rocket.png`
    *   Specifies the visual representation of the Rocket card in the game's UI.

### `ItemActionComponent`

*   **`_tags`**: `enabled_in_world`
    *   This tag ensures the item is active and functional when present in the game world.
*   **`action_id`**: `ROCKET`
    *   Assigns a unique identifier to this item's action, likely used by the game's scripting system to trigger its effects.

## Transform and Visual Effects

These components define how the item behaves when held and the visual feedback it provides.

### `InheritTransformComponent`

*   **`_tags`**: `enabled_in_world,enabled_in_hand`
    *   Makes the transform properties active when the item is in the world and specifically when held by the player.
*   **`parent_hotspot_tag`**: `shoot_pos`
    *   The item's transform will align with the `shoot_pos` hotspot of its parent (likely the player's wand), determining its orientation and position when used.

### `ParticleEmitterComponent`

This component generates cosmetic particles to enhance the visual flair of the Rocket card when held.

*   **`_tags`**: `enabled_in_hand,item_identified`
    *   Particles are emitted when the item is held and has been identified by the player.
*   **`emitted_material_name`**: `spark`
    *   The type of particle to be emitted.
*   **`offset.x`, `offset.y`**: `0`
    *   The center of the particle emission relative to the item's hotspot.
*   **`x_pos_offset_min`/`max`**: `-2` to `2`
*   **`y_pos_offset_min`/`max`**: `2` to `-2`
    *   Defines a small area around the hotspot from which particles can originate.
*   **`x_vel_min`/`max`**: `-2` to `2`
*   **`y_vel_min`/`max`**: `-20` to `-10`
    *   Controls the initial velocity of the emitted particles, giving them an upward trajectory.
*   **`count_min`/`max`**: `1` to `2`
    *   The number of particles emitted per burst.
*   **`lifetime_min`/`max`**: `0.2` to `0.3`
    *   The duration each particle exists.
*   **`create_real_particles`**: `0`
    *   Indicates these are cosmetic particles, not physical entities.
*   **`emit_cosmetic_particles`**: `1`
    *   Enables the emission of cosmetic particles.
*   **`emission_interval_min_frames`/`max_frames`**: `8` to `15`
    *   The delay between particle emission bursts.
*   **`is_emitting`**: `1`
    *   Ensures the particle emitter is active.

### `LightComponent`

This component adds a light source to the Rocket card when held, providing visual feedback.

*   **`_tags`**: `enabled_in_hand,item_identified`
    *   The light is active when the item is held and identified.
*   **`_enabled`**: `1`
    *   Enables the light component.
*   **`radius`**: `30`
    *   The range of the light.
*   **`fade_out_time`**: `1.5`
    *   How long the light takes to fade.
*   **`r`, `g`, `b`**: `120`, `70`, `5`
    *   Defines the color of the light (a warm, orange hue).