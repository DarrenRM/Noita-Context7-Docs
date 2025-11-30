---
title: Fire Protection Effect
category: entities
---

# Fire Protection Effect

This entity defines a game effect that grants the player protection against fire damage.

## Entity Definition

The core of this entity is the `GameEffectComponent`.

### Key Components

*   **`GameEffectComponent`**: This component is responsible for defining the actual game effect.
    *   **`_tags`**: "effect\_protection" - Indicates this is a protective effect.
    *   **`effect`**: "PROTECTION\_FIRE" - Specifies the type of protection granted, in this case, fire.
    *   **`frames`**: "-1" - This signifies that the effect is permanent or lasts indefinitely until removed by other means.
    *   **`exclusivity_group`**: "0" - This likely means this effect can coexist with other effects in group 0. If it were a different number, it might imply that only one effect from that group can be active at a time.

### Inheritance

*   **`InheritTransformComponent`**: This component is present but empty. It typically handles the entity's position, rotation, and scale, but in this case, it doesn't seem to apply any specific transformations, suggesting the effect is purely a status modifier.