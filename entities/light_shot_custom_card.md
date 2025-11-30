---
title: Light Shot Custom Card
category: entities
---

# Light Shot Custom Card

This document describes the `light_shot.xml` entity, which defines a custom spell card in Noita. This card, when picked up, grants the player the "Light Shot" action.

## Key Components

### Base Entity Configuration

The entity inherits its core functionality from `data/entities/base_custom_card.xml`.

*   **`SpriteComponent`**:
    *   `image_file`: `data/ui_gfx/gun_actions/light_shot.png` - This specifies the visual icon for the Light Shot spell card in the player's inventory and spell selection UI.

### Action and Behavior

*   **`ItemActionComponent`**:
    *   `_tags`: `enabled_in_world` - Indicates that this action is available for use when the player is in the game world.
    *   `action_id`: `LIGHT_SHOT` - This is the unique identifier for the spell action.

### Visual Effects

This section defines particle effects associated with the spell.

*   **`SpriteParticleEmitterComponent`**:
    *   `sprite_file`: `data/particles/tinyspark_03.xml` - This points to the particle definition for small sparks, which are likely emitted when the spell is cast or as a visual flourish.
    *   `emission_interval_min_frames`: `15`
    *   `emission_interval_max_frames`: `25` - These attributes control the timing of particle emissions, creating a dynamic visual effect.

### Inheritance

*   The entity also inherits from `data/entities/misc/custom_cards/base_damage.xml`, suggesting it might contribute some base damage properties or other common attributes shared by damage-dealing custom cards.