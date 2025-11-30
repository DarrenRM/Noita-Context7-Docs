---
title: Accelerating Shot Custom Card
category: entities
---

# Accelerating Shot Custom Card

This document details the `accelerating_shot.xml` entity, which defines a custom spell card in Noita. This card, when equipped, modifies projectile behavior to increase its speed over time.

## Base Entity Configuration

The core of this custom card is built upon `base_custom_card.xml`, providing fundamental properties for spell cards.

### Sprite Component

Defines the visual representation of the card in the game's UI.

*   **`image_file`**: `data/ui_gfx/gun_actions/accelerating_shot.png` - Specifies the texture used for the card's icon.

### Item Action Component

Assigns a unique identifier to the action performed by this card.

*   **`action_id`**: `ACCELERATING_SHOT` - This ID is used internally by the game to recognize and apply the card's effect.
*   **`_tags`**: `enabled_in_world` - Indicates that this action is active when the item is present in the game world.

## Transform Component

Manages the positioning and orientation of the card when held by the player.

### Inherit Transform Component

*   **`parent_hotspot_tag`**: `shoot_pos` - The card's transform will inherit from the `shoot_pos` of its parent (typically the player's wand), aligning its visual and functional origin with the firing point.
*   **`_tags`**: `enabled_in_world`, `enabled_in_hand` - The transform is active when the item is in the world and specifically when held by the player.

## Particle Emitter Component

This component adds visual flair by emitting cosmetic particles when the card is held and identified.

*   **`_tags`**: `enabled_in_hand`, `item_identified` - Particles are emitted only when the player is holding the item and it has been identified.
*   **`emitted_material_name`**: `spark_green` - The type of particle to be emitted.
*   **`offset.x`, `offset.y`**: `0` - The center of the emission relative to the parent's hotspot.
*   **`x_pos_offset_min`, `x_pos_offset_max`**: `-3` to `3` - The horizontal spread of particle emission.
*   **`y_pos_offset_min`, `y_pos_offset_max`**: `1` to `-1` - The vertical spread of particle emission.
*   **`x_vel_min`, `x_vel_max`**: `-10` to `10` - The horizontal velocity range of emitted particles.
*   **`y_vel_min`, `y_vel_max`**: `-20` to `-10` - The upward vertical velocity range of emitted particles.
*   **`count_min`, `count_max`**: `1` - The number of particles emitted per burst.
*   **`lifetime_min`, `lifetime_max`**: `0.4` to `0.5` - The duration each particle exists.
*   **`create_real_particles`**: `0` - Particles are cosmetic and do not interact physically.
*   **`emit_cosmetic_particles`**: `1` - Enables the emission of cosmetic particles.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `20` to `32` - The frame delay between particle emission bursts.
*   **`is_emitting`**: `1` - The particle emitter is active by default.