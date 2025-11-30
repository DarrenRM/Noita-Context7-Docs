---
title: Mana Reduce Custom Card
category: entities
---

# Mana Reduce Custom Card

This document describes the `mana_reduce.xml` entity, which defines a custom card in Noita that reduces mana cost.

## Entity Definition

The core of this entity is based on `base_custom_card.xml`, providing standard functionality for custom cards.

### Key Components

*   **SpriteComponent**:
    *   `image_file`: `data/ui_gfx/gun_actions/mana.png` - Specifies the visual representation of the card in the UI.

*   **ItemActionComponent**:
    *   `action_id`: `MANA_REDUCE` - This is the unique identifier for the action this card performs, indicating it reduces mana costs.
    *   `_tags`: `enabled_in_world` - The action is active when the card is in the game world.

*   **InheritTransformComponent**:
    *   `parent_hotspot_tag`: `shoot_pos` - The card's transform is inherited from the `shoot_pos` of its parent, typically the player's wand.
    *   `_tags`: `enabled_in_world`, `enabled_in_hand` - The transform inheritance is active when the card is in the world or held by the player.

*   **ParticleEmitterComponent**:
    *   `emitted_material_name`: `plasma_fading` - Defines the material used for cosmetic particles.
    *   `offset.x`, `offset.y`: `0` - Particles are emitted from the center of the card.
    *   `x_pos_offset_min`/`max`, `y_pos_offset_min`/`max`: Defines a small area around the card for particle emission.
    *   `x_vel_min`/`max`, `y_vel_min`/`max`: Controls the initial velocity of the emitted particles.
    *   `count_min`/`max`: `1` - A single particle is emitted per emission cycle.
    *   `lifetime_min`/`max`: `0.2` to `0.3` seconds - Controls how long particles last.
    *   `create_real_particles`: `0` - Only cosmetic particles are created, not actual game entities.
    *   `emit_cosmetic_particles`: `1` - Enables the emission of cosmetic particles.
    *   `emission_interval_min_frames`/`max_frames`: `10` to `25` frames - Controls the frequency of particle emissions.
    *   `is_emitting`: `1` - The particle emitter is active.

This entity primarily serves as a visual and functional placeholder for a mana-reducing effect, likely intended to be combined with other game mechanics or scripts to implement the actual mana reduction logic.