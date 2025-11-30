---
title: Effect Apply On Fire Entity
category: entities
---

# Effect Apply On Fire Entity

This entity defines a component that applies a specific game effect when the entity is on fire.

## Key Components

### `GameEffectComponent`

This component is responsible for applying a game effect.

*   **`effect`**: The name of the game effect to apply. In this case, it's `"ON_FIRE"`.
*   **`frames`**: The duration (in frames) for which the effect will be applied. Here, it's set to `720` frames.

### `InheritTransformComponent`

This component is present but has no specific configurations in this example. It typically handles the inheritance of transform properties from parent entities.

*   **`_enabled`**: Set to `"1"`, indicating the component is active.