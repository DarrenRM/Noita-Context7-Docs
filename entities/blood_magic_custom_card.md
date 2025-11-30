---
title: Blood Magic Custom Card
category: entities
---

# Blood Magic Custom Card

This document describes the `blood_magic.xml` entity, which defines a custom card in Noita that utilizes blood magic.

## Entity Definition

The core of this entity is based on `base_custom_card.xml`, providing standard functionality for custom cards.

### Key Components

*   **`SpriteComponent`**:
    *   `image_file`: `data/ui_gfx/gun_actions/blood_magic.png` - Specifies the visual representation of the card in the UI.

*   **`ItemActionComponent`**:
    *   `_tags`: `enabled_in_world` - Indicates the card is active and usable within the game world.
    *   `action_id`: `BLOOD_MAGIC` - Assigns a unique identifier for this action.

*   **`InheritTransformComponent`**:
    *   `_tags`: `enabled_in_world,enabled_in_hand` - Ensures the card's transform properties are applied when in the world and held by the player.
    *   `parent_hotspot_tag`: `shoot_pos` - Links the card's position to the player's shooting position.

*   **`ParticleEmitterComponent`**:
    *   `_tags`: `enabled_in_hand,item_identified` - Activates the particle effect when the item is held and identified.
    *   `emitted_material_name`: `blood` - The material that will be emitted as particles.
    *   `offset.x`, `offset.y`: Controls the particle emission origin relative to the card.
    *   `x_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_min`, `y_pos_offset_max`: Defines the area where particles can spawn.
    *   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Sets the initial velocity range for emitted particles.
    *   `count_min`, `count_max`: Determines the number of particles emitted per burst.
    *   `lifetime_min`, `lifetime_max`: Controls how long each particle exists.
    *   `create_real_particles`: `0` - Indicates that these are cosmetic particles, not physical entities.
    *   `emit_cosmetic_particles`: `1` - Confirms that cosmetic particles are being emitted.
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: Sets the delay between particle emission bursts.
    *   `is_emitting`: `1` - Ensures the particle emitter is active.

This entity primarily defines the visual and functional aspects of the "Blood Magic" custom card, including its UI representation, action ID, and a cosmetic particle effect that emits "blood" when the card is active.