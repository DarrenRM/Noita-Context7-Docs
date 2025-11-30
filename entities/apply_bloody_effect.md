---
title: Apply Bloody Effect
category: entities
---

# Apply Bloody Effect

This entity applies the "BLOODY" status effect to entities that interact with it.

## Key Components

### GameEffectComponent

This component defines the status effect to be applied and its duration.

| Attribute | Description                                  |
| :-------- | :------------------------------------------- |
| `effect`  | The name of the status effect to apply.      |
| `frames`  | The duration of the effect in game frames.   |

**Example:**

```xml
<GameEffectComponent 
    effect="BLOODY"
    frames="720"
>
</GameEffectComponent >
```