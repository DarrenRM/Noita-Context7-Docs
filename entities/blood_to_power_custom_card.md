---
title: Blood to Power Custom Card
category: entities
---

# Blood to Power Custom Card

This document details the `blood_to_power.xml` entity, which defines a custom card in Noita that converts blood into magical power.

## Core Components

### Base Entity

The card inherits from `base_custom_card.xml`, providing fundamental properties for custom cards.

*   **`SpriteComponent`**:
    *   `image_file`: `data/ui_gfx/gun_actions/blood_punch.png` - This defines the visual representation of the card in the UI.

*   **`ItemActionComponent`**:
    *   `action_id`: `BLOOD_TO_POWER` - This unique identifier links the card to its specific in-game action.
    *   `_tags`: `enabled_in_world` - The action is active when the card is in the game world.

### Transform Component

*   **`InheritTransformComponent`**:
    *   `_tags`: `enabled_in_world,enabled_in_hand` - The transform is applied when the card is in the world or held by the player.
    *   `parent_hotspot_tag`: `shoot_pos` - The card's transform is relative to the player's shooting position.

### Particle Emitter

This component creates cosmetic particles when the card is held and identified.

*   **`ParticleEmitterComponent`**:
    *   `_tags`: `enabled_in_hand,item_identified` - Particles are emitted when the item is held and its identity is revealed.
    *   `emitted_material_name`: `blood` - The particles emitted are visually represented as blood.
    *   `offset.x`, `offset.y`: `0` - The emitter is centered on the card.
    *   `x_pos_offset_min/max`, `y_pos_offset_min/max`: Defines a small area around the card for particle origin.
    *   `x_vel_min/max`, `y_vel_min/max`: Controls the initial velocity and direction of the emitted particles, giving them an upward, slightly outward motion.
    *   `count_min/max`: `1` - A single particle is emitted per emission cycle.
    *   `lifetime_min/max`: `0.2` to `0.3` seconds - The duration each particle exists.
    *   `create_real_particles`: `0` - These are cosmetic particles, not physical entities.
    *   `emit_cosmetic_particles`: `1` - Explicitly enables cosmetic particle emission.
    *   `emission_interval_min_frames/max_frames`: `10` to `25` frames - Controls the rate at which particles are emitted.
    *   `is_emitting`: `1` - The particle emitter is active by default.