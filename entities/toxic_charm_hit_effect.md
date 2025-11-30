---
title: Toxic Charm Hit Effect
category: entities
---

# Toxic Charm Hit Effect

This entity defines a special hit effect that triggers when a specific status condition is met.

## Key Components

### HitEffectComponent

This component governs the behavior when the entity is hit.

*   **condition_status**: `RADIOACTIVE` - The status effect that must be present on the target for this hit effect to trigger.
*   **effect_hit**: `LOAD_UNIQUE_GAME_EFFECT` - Specifies the type of effect to load.
*   **value_string**: `data/entities/misc/effect_charm_short.xml` - The path to the game effect XML file that will be loaded and applied when the conditions are met. This likely defines the visual and/or functional outcome of the "toxic charm" effect.