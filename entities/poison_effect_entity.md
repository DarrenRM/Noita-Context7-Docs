---
title: Poison Effect Entity
category: entities
---

# Poison Effect Entity

This entity defines the properties of the "POISON" game effect in Noita.

## Key Components

### GameEffectComponent

This component governs the behavior and duration of the poison effect.

*   **`effect`**: Specifies the type of effect. In this case, it's `"POISON"`.
*   **`frames`**: Determines the duration of the effect in game frames. A value of `600` frames translates to approximately 10 seconds (assuming 60 frames per second).

### InheritTransformComponent

This component is present but empty, indicating that the entity inherits its transform properties from its parent or context. It doesn't add any specific transform behavior on its own.