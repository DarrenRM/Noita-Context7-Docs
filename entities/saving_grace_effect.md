---
title: Saving Grace Effect
category: entities
---

# Saving Grace Effect

This entity defines the "Saving Grace" game effect in Noita.

## Key Components

### GameEffectComponent
This component is responsible for applying the game effect.

*   **`effect`**: Specifies the type of effect. In this case, it's `"SAVING_GRACE"`.
*   **`frames`**: The duration of the effect in frames. Here, it's set to `600` frames (which translates to 10 seconds at 60 FPS).

## XML Structure

```xml
<Entity>
    <InheritTransformComponent>
    </InheritTransformComponent>    
    
    <GameEffectComponent 
        effect="SAVING_GRACE"
        frames="600"
    >
	</GameEffectComponent >

</Entity>
```