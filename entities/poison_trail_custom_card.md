---
title: Poison Trail Custom Card
category: entities
---

# Poison Trail Custom Card

This document describes the `poison_trail.xml` entity, which defines a custom card in Noita that creates a trail of poison gas when held.

## Base Entity

The card inherits from `base_custom_card.xml`, providing core functionality for custom cards.

### Sprite Component

*   **`image_file`**: `data/ui_gfx/gun_actions/poison_trail.png` - This specifies the visual representation of the card in the UI.

### Item Action Component

*   **`action_id`**: `POISON_TRAIL` - This unique identifier links the card to its specific in-game action.
*   **`_tags`**: `enabled_in_world` - The action is active when the card is in the game world.

## Inheritance and Transform

### Inherit Transform Component

*   **`_tags`**: `enabled_in_world`, `enabled_in_hand` - The transform is applied when the card is in the world and specifically when held in hand.
*   **`Transform`**:
    *   `position.x`: `5`
    *   `position.y`: `0` - This defines a slight offset for the card's visual position.

## Particle Emitter Component

This component is responsible for generating the poison gas trail.

*   **`_tags`**: `enabled_in_hand`, `item_identified` - The particle emission occurs when the item is held and has been identified by the player.
*   **`emitted_material_name`**: `poison_gas` - The type of material that will be emitted as particles.
*   **`offset.x`**, **`offset.y`**: `0` - The emission originates from the center of the card.
*   **`x_pos_offset_min`**: `-5`, **`x_pos_offset_max`**: `5` - Random horizontal offset for particle spawn.
*   **`y_pos_offset_min`**: `2`, **`y_pos_offset_max`**: `-2` - Random vertical offset for particle spawn.
*   **`x_vel_min`**: `-2`, **`x_vel_max`**: `2` - Random horizontal velocity for emitted particles.
*   **`y_vel_min`**: `-20`, **`y_vel_max`**: `-10` - Upward velocity for emitted particles, creating a trail effect.
*   **`count_min`**: `1`, **`count_max`**: `1` - Emits a single particle per emission cycle.
*   **`lifetime_min`**: `0.2`, **`lifetime_max`**: `0.3` - The duration each particle exists.
*   **`create_real_particles`**: `1` - Creates actual game particles.
*   **`emit_cosmetic_particles`**: `1` - Also emits visual-only particles for a richer effect.
*   **`emission_interval_min_frames`**: `10`, **`emission_interval_max_frames`**: `25` - The delay between particle emission bursts.
*   **`is_emitting`**: `1` - The particle emitter is active.