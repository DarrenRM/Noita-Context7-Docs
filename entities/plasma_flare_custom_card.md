---
title: Plasma Flare Custom Card
category: entities
---

# Plasma Flare Custom Card

This document describes the `plasma_flare.xml` entity, which defines a custom spell card in Noita.

## Core Components

### Base Entity Configuration

*   **`Base file="data/entities/base_custom_card.xml"`**: Inherits fundamental properties of a custom spell card.
    *   **`SpriteComponent`**: Defines the visual representation of the card in the UI.
        *   `image_file="data/ui_gfx/gun_actions/plasma_flare.png"`: Specifies the sprite used for the Plasma Flare card.

### Action and Behavior

*   **`ItemActionComponent`**: Assigns an action ID to the card, enabling its use in the game.
    *   `_tags="enabled_in_world"`: Indicates the card is usable when found in the game world.
    *   `action_id="PLASMA_FLARE"`: The unique identifier for the Plasma Flare spell action.

### Visual Effects

*   **`Base file="data/entities/misc/custom_cards/base_laser.xml"`**: Inherits visual effects commonly associated with laser-like spells.
    *   **`SpriteParticleEmitterComponent`**: Controls the emission of particles that create a shimmering effect.
        *   `sprite_file="data/particles/shine_pink.xml"`: Uses a pink shine particle sprite.
        *   `emission_interval_min_frames="35"`: Minimum frames between particle emissions.
        *   `emission_interval_max_frames="45"`: Maximum frames between particle emissions.
    *   **`ParticleEmitterComponent`**: Manages the emission of the primary spell material.
        *   `emitted_material_name="plasma_fading_pink"`: Specifies that the emitted material is a fading pink plasma.