---
title: Acid Shot Custom Card
category: entities
---

# Acid Shot Custom Card

This document details the `acidshot.xml` entity, which defines a custom spell card in Noita that shoots acid.

## Base Entity

The card inherits from `base_custom_card.xml`, providing core functionality for custom spells.

### Key Components:

*   **SpriteComponent**: Defines the visual representation of the card in the UI.
    *   `image_file`: `data/ui_gfx/gun_actions/acidshot.png` - The icon for the Acid Shot card.
*   **ItemActionComponent**: Assigns an action ID to the card.
    *   `action_id`: `ACIDSHOT` - Identifies the spell action.

## Visual Effects (Particle Emitters)

The card has two particle emitters that create visual effects when the item is held and identified.

### Particle Emitter 1 (Acid Gas)

This emitter simulates the acidic nature of the spell.

*   **`emitted_material_name`**: `acid_gas` - The material that forms the particles.
*   **`offset.x`, `offset.y`**: `0, 0` - Particles originate from the center of the item.
*   **`x_pos_offset_min/max`, `y_pos_offset_min/max`**: Defines the spread of particles around the origin.
*   **`x_vel_min/max`, `y_vel_min/max`**: Controls the initial velocity and direction of the particles.
*   **`count_min/max`**: `1, 1` - Emits a single particle per emission.
*   **`lifetime_min/max`**: `0.2, 0.3` - Duration each particle exists.
*   **`create_real_particles`**: `1` - Creates actual game particles.
*   **`emit_cosmetic_particles`**: `1` - Also emits visual-only particles.
*   **`emission_interval_min_frames/max_frames`**: `10, 25` - Controls how often particles are emitted.
*   **`is_emitting`**: `1` - The emitter is active.

### Particle Emitter 2 (Radioactive Liquid Fading)

This emitter adds a secondary visual effect, possibly representing a fading corrosive element.

*   **`emitted_material_name`**: `radioactive_liquid_fading` - The material for these particles.
*   **`offset.x`, `offset.y`**: `0, 0` - Originates from the center.
*   **`x_pos_offset_min/max`, `y_pos_offset_min/max`**: Defines the spread.
*   **`x_vel_min/max`, `y_vel_min/max`**: Controls particle velocity.
*   **`count_min/max`**: `5, 5` - Emits 5 particles per emission.
*   **`lifetime_min/max`**: `0.1, 0.6` - Duration each particle exists.
*   **`create_real_particles`**: `0` - Does not create real game particles, only cosmetic.
*   **`emit_cosmetic_particles`**: `1` - Emits visual-only particles.
*   **`emission_interval_min_frames/max_frames`**: `15, 25` - Emission frequency.
*   **`is_emitting`**: `1` - The emitter is active.