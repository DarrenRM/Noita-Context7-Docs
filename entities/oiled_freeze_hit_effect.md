---
title: Oiled Freeze Hit Effect
category: entities
---

# Oiled Freeze Hit Effect

This entity defines a special hit effect that triggers when an entity is hit while in the "OILED" status.

## HitEffectComponent

This component governs the behavior of hit effects.

### Key Attributes:

*   **`condition_status`**: Specifies the status condition that must be met for this effect to trigger. In this case, it's `"OILED"`.
*   **`effect_hit`**: Determines the type of effect to load when the condition is met. `"LOAD_UNIQUE_GAME_EFFECT"` indicates a specific, pre-defined game effect.
*   **`value_string`**: Provides the path to the XML file defining the actual game effect to be loaded. Here, it points to `"data/entities/misc/effect_frozen.xml"`, meaning the entity will be frozen.