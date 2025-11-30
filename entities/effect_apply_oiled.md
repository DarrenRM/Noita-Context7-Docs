---
title: Effect Apply Oiled
category: entities
---

# Effect Apply Oiled

This entity applies the "OILED" status effect to entities.

## Key Components

### `GameEffectComponent`

This component defines the status effect to be applied and its duration.

*   **`effect`**: Specifies the type of status effect. In this case, it's `"OILED"`.
*   **`frames`**: The duration of the effect in game frames. `720` frames is equivalent to 12 seconds (720 frames / 60 frames per second).

### `InheritTransformComponent`

This component is present but has no specific configurations, indicating it inherits default transform properties.

## Usage

This entity is typically used in conjunction with other game mechanics or spells that trigger status effects. When this entity is spawned, it will apply the "OILED" effect to any entity it interacts with or is applied to.