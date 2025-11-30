---
title: Damage Friendly Custom Card
category: entities
---

# Damage Friendly Custom Card

This document describes the `damage_friendly.xml` entity, which defines a custom card in Noita that deals damage to friendly entities.

## Key Components

### Base Entity (`base_custom_card.xml`)

This entity inherits its core functionality from `base_custom_card.xml`.

### Sprite Component

*   **`image_file`**: `data/ui_gfx/gun_actions/damage_friendly.png`
    *   This specifies the visual representation of the card in the game's UI.

### Item Action Component

*   **`_tags`**: `enabled_in_world`
    *   Indicates that this action is available and can be used while in the game world.
*   **`action_id`**: `DAMAGE_FRIENDLY`
    *   This is the unique identifier for the action performed by this card.

### Base Damage Component (`base_damage.xml`)

This entity also inherits from `base_damage.xml`, which likely provides the underlying mechanics for dealing damage. The specific damage values and targeting behavior would be defined in this base file.