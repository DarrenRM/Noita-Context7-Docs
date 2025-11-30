---
title: Polymorph Protection Effect
category: entities
---

# Polymorph Protection Effect

This entity defines a game effect that grants the player protection against polymorphing.

## Entity Definition

The core of this entity is the `GameEffectComponent`.

### Key Components

*   **`GameEffectComponent`**:
    *   `_tags`: "effect\_protection" - Identifies this as a protection effect.
    *   `effect`: "PROTECTION\_POLYMORPH" - Specifies the type of protection granted.
    *   `frames`: "7200" - The duration of the effect in game frames (7200 frames is equivalent to 2 minutes).

### Other Components

*   **`InheritTransformComponent`**: This component is present but has no specific configurations, indicating it inherits default transform properties.