---
title: Heavy Shot Custom Card
category: entities
---

# Heavy Shot Custom Card

This document describes the `heavy_shot.xml` entity, which defines a custom spell card in Noita. This card, when picked up, grants the player the "Heavy Shot" action.

## Key Components

### Base Entity Configuration

The entity inherits its core functionality from `base_custom_card.xml`.

*   **`SpriteComponent`**: Defines the visual representation of the card in the game's UI.
    *   `image_file`: `data/ui_gfx/gun_actions/heavy_shot.png` - Specifies the texture used for the card's icon.

### Action and Gameplay

*   **`ItemActionComponent`**: Assigns an action ID to the card, making it usable by the player.
    *   `_tags`: `enabled_in_world` - Indicates that this action is available when the player is in the game world.
    *   `action_id`: `HEAVY_SHOT` - The unique identifier for the Heavy Shot spell action.

### Visual Effects

The entity also incorporates visual effects from `base_damage.xml`.

*   **`SpriteParticleEmitterComponent`**: Controls the emission of particles associated with the spell's activation or impact.
    *   `sprite_file`: `data/particles/tinyspark_01.xml` - The particle effect used.
    *   `emission_interval_min_frames`: `15` - Minimum frames between particle emissions.
    *   `emission_interval_max_frames`: `25` - Maximum frames between particle emissions.