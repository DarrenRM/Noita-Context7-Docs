---
title: Curse Wither Melee Hit Effect
category: entities
---

# Curse Wither Melee Hit Effect

This entity defines the visual and functional effect that occurs when a melee attack applies the "Curse Wither" status.

## Key Components

### HitEffectComponent

This component dictates what happens when the entity is triggered as a hit effect.

*   **`effect_hit`**: Specifies the type of effect to load.
    *   `LOAD_UNIQUE_CHILD_ENTITY`: Indicates that a unique child entity will be loaded.
*   **`value_string`**: The path to the entity that will be loaded as the hit effect.
    *   `data/entities/misc/curse_wither_melee.xml`: This points to the actual entity responsible for the "Curse Wither" melee effect.

## Usage

This entity acts as a placeholder or trigger for the more complex `curse_wither_melee.xml` entity, ensuring that the appropriate visual and gameplay effects are applied during combat.