---
title: Alcohol Blast Custom Card
category: entities
---

# Alcohol Blast Custom Card

This document details the `alcohol_blast.xml` entity, representing a custom spell card in Noita.

## Base Entity

The card inherits from `base_custom_card.xml`, providing core functionality for custom spell cards.

### Key Components:

*   **SpriteComponent**: Defines the visual representation of the card in the UI.
    *   `image_file`: `data/ui_gfx/gun_actions/alcohol_blast.png` - Specifies the sprite used for the card.
*   **ItemActionComponent**: Links the card to a specific in-game action.
    *   `_tags`: `enabled_in_world` - Indicates the card is active and usable in the game world.
    *   `action_id`: `ALCOHOL_BLAST` - The unique identifier for the spell action.

## Transform and Visuals

### InheritTransformComponent:

This component manages the card's position and orientation when held.

*   `_tags`: `enabled_in_world`, `enabled_in_hand` - Ensures the transform is applied when the card is in the world and being held.
*   **Transform**:
    *   `position.x`: `4` - Offset on the X-axis.
    *   `position.y`: `0` - Offset on the Y-axis.

## Particle Effects

### ParticleEmitterComponent:

This component defines the visual particle effects associated with the card when it's held.

*   `_tags`: `enabled_in_hand`, `item_identified` - The emitter is active when the item is held and identified.
*   `emitted_material_name`: `spark` - The type of material used for the emitted particles.
*   `offset.x`, `offset.y`: `0`, `0` - The center point of the emission relative to the card.
*   `x_pos_offset_min`, `x_pos_offset_max`: `-5`, `5` - Range for horizontal position offset of particles.
*   `y_pos_offset_min`, `y_pos_offset_max`: `2`, `-2` - Range for vertical position offset of particles.
*   `x_vel_min`, `x_vel_max`: `-2`, `2` - Range for horizontal velocity of particles.
*   `y_vel_min`, `y_vel_max`: `-20`, `-10` - Range for vertical velocity of particles.
*   `count_min`, `count_max`: `1`, `1` - Number of particles emitted per burst.
*   `lifetime_min`, `lifetime_max`: `0.2`, `0.3` - Duration of each particle in seconds.
*   `create_real_particles`: `1` - Whether to create actual game physics particles.
*   `emit_cosmetic_particles`: `1` - Whether to emit purely visual particles.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: `10`, `25` - The frame interval between particle emissions.
*   `is_emitting`: `1` - Enables the particle emission.